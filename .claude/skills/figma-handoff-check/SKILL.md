---
name: figma-handoff-check
description: Check a Figma design file before it goes to engineering. Flags misleading or duplicate screen names, default layer names, hardcoded or primitive tokens, off-system text styles, detached and local components, and missing responsive variants, then writes a short change summary for devs. Use when someone asks for a handoff check, asks whether a file is ready for dev, wants a Figma file cleaned up, or shares a Figma link before handoff. Report-only; it never edits the file.
---
 
# Figma handoff check
 
Checks a Figma file, or one page or section of it, before it goes to engineering. More developers now build with AI coding tools that read layer names and token bindings as context. A messy file becomes messy code: `Frame1597880841` with a raw hex value instead of `AppointmentCard` with a semantic token. This check catches that before handoff.
 
**Report-only.** It never changes the file. It produces a report the designer works through, or approves fixes for in a later step.
 
## Load design system context
 
If a filled-in design-system context file exists for the product (copy [references/design-system-context.template.md](references/design-system-context.template.md) and fill it in once per product), read it first. It holds the answers this skill would otherwise ask for: platforms, breakpoints, which token collections are semantic or primitive, the spacing source of truth, and the screen naming pattern.
 
When the user answers one of those questions during a run, suggest adding the answer to the context file so it isn't asked again.
 
If no context file exists, ask for what's missing in one compact question. Don't invent tokens, breakpoints or naming rules.
 
## Inputs
 
1. A Figma design link (`/design/` URL), ideally with a `node-id` for the page or section being handed off.
2. The platform or product surface the file is for, if the context file lists more than one.
3. Optional: the previous handoff report for this file, so the change summary can compare against it.
If the link points at a whole page with several sections, list the sections with their screen counts and ask which to check. Recommend the smallest section that's still a real handoff. Don't guess the scope.
 
## Tools
 
This skill uses the Figma MCP server.
 
- `get_metadata`: the layer tree. On a full page the output is often too large and gets saved to a file; parse it with python or jq (list sections and top-level frames first, then drill in). Use it to read what's inside a frame before suggesting a name.
- `get_screenshot`: only when the layer tree isn't enough to tell what a frame is.
- `search_design_system`: send one query per call, since the server may drop extra queries. Pass `includeLibraryKeys` to restrict results to the source-of-truth library.
- `use_figma`: read-only scan scripts. Load the `figma-use` skill before the first `use_figma` call. Scripts must not modify any node. Don't import library variables or components to read their values (for example with `importVariableByKeyAsync`); importing changes the file. If a value can't be read another way, report it as unconfirmed.
## Always skip
 
Canvas annotation layers are not part of the screens. Skip them in every check: annotation header components, sticky notes, dev annotation callouts, connector arrows, loose text labels and lines placed directly in the section, and section outline strokes. Adjust the skip list in the scan script to match the annotation components your team uses.
 
Don't descend into component instances, and don't count an instance's own padding, fills or radius. Those come from the component. Only the designer's own frames, groups, text and shapes count.
 
## The checks
 
Each finding gets a severity:
 
- **Blocker**: will produce wrong or messy code, or will mislead developers. Examples: detached component, hardcoded color, primitive token where a semantic one exists, screen name that contradicts its content.
- **Fix before handoff**: hurts developer or AI understanding. Examples: default layer names, inconsistent screen naming, local component that needs a decision, off-system text style.
- **Nice to have**: tidy-up, or a design system gap the designer can't fix alone.
### 1. Screen names: duplicates and contradictions
 
For every top-level screen in scope:
 
- Flag duplicate names. For each duplicate, read what's inside and say how they differ.
- Flag names that contradict the content, such as "No results" on a screen that shows results. This is a blocker, because a developer or their AI tool will trust the name.
- Flag suffixes like `(2)`, `copy`, `v2`, `new` or `final`, and ask whether each is a version or a leftover.
- Flag mixed naming patterns across screens (`Flow / Screen`, `Screen - State`, `Screen, State`). Suggest the pattern from the context file, or `Platform / Flow / Screen / State` if there isn't one. Match the file's own convention when one is clearly dominant.
### 2. Default layer names
 
Flag frames, groups and components with default names such as `Frame 123`, `Group 45`, `Rectangle 12` or `Frame 1948758688`, or no name. Only flag structural layers: top-level screens, sections, and containers with children. Suggest a PascalCase name based on what's inside (`SidebarTop`, `NotesFilter`, `ResourcesList`). If the layer sits inside a detached component, note that relinking the component fixes it.
 
Generic but meaningful names like `Image frame` or `Container` go under nice to have, grouped as one finding with a count.
 
Flag hidden loose layers in the section as nice to have.
 
### 3. Hardcoded values and primitive tokens
 
For fills and strokes on the designer's own layers:
 
- **Hardcoded color** with no variable or style bound: blocker.
- **Primitive-bound color** (a collection the context file marks as primitive, or one named like `primitive`, `core`, `base`, `palette` or `global`) where a semantic token exists: blocker. If collections don't follow an obvious pattern and the context file doesn't cover them, list them and ask once.
For auto layout padding and gap, and corner radius:
 
- Group unbound values by value (`gap 16 x29`) with typical layer names.
- Base the severity on the spacing source of truth. If it has a token for that value and role, it's fix before handoff. If it has no fitting token, it's nice to have, framed as a design system gap. Say whether the values follow a clean scale; that's useful evidence for design system work.
### 4. Off-system text styles
 
Flag text layers with no text style, mixed styles, or a local style that isn't from the library. Suggest the closest library style.
 
### 5. Detached and local components
 
- **Detached components** (frames with `detachedInfo`): blocker. Group by name with count, screens and node links. The name usually still matches the library component, so say which one to swap back to. Note that a detach may have been on purpose; if so, it's a component gap to raise with the design system team.
- **Local components** (instances whose main component isn't from a library): fix before handoff, framed as a decision. Move it into the design system, or keep it project-only and tell developers it's new.
### 6. Responsive variants
 
Use the breakpoints from the context file, or ask. If the surface is desktop only, skip this check and say so in the report header. Otherwise flag screens missing a variant, and states that exist at one breakpoint but not another.
 
### 7. Out-of-scope neighbours
 
List top-level frames on the same page that sit next to the scanned section but outside it. Say they weren't scanned.
 
### 8. Change summary for developers
 
Write a plain-language summary of what's in the handoff: screens and states covered, new or changed components, and anything needing a developer decision. Compare against the previous report if there is one; otherwise say this is the baseline. Keep it readable in under a minute.
 
## Read-only scan script (for `use_figma`)
 
Adapt as needed. Switch to the right page first, scan only the scoped node, and return aggregated results so large files don't flood context. Run a second, targeted script when you need detail, such as spacing values by layer name.
 
```js
const page = await figma.getNodeByIdAsync(PAGE_ID);
await figma.setCurrentPageAsync(page);
const root = await figma.getNodeByIdAsync(SECTION_ID);
const SKIP = /^(Annotation Header|Sticky Note|Dev annotation)$/;
const DEFAULT_NAME = /^(Frame|Group|Rectangle|Ellipse|Vector|Line)\s*\d+$/i;
const GENERIC_NAME = /^(Image frame|Container|Content|Wrapper)$/i;
const hex = c => '#' + [c.r,c.g,c.b].map(v => Math.round(v*255).toString(16).padStart(2,'0')).join('');
const out = { screens: [], defaultNames: [], genericNames: 0, hardcodedFills: {}, boundColl: {}, spacing: {}, text: {}, detached: [], localComponents: {}, scanned: 0 };
const vc = {}, cc = {};
async function coll(id) {
  if (vc[id]) return vc[id];
  const v = await figma.variables.getVariableByIdAsync(id);
  if (!v) return (vc[id] = { token: '?', collection: '?' });
  if (!cc[v.variableCollectionId]) { const c = await figma.variables.getVariableCollectionByIdAsync(v.variableCollectionId); cc[v.variableCollectionId] = c ? c.name : '?'; }
  return (vc[id] = { token: v.name, collection: cc[v.variableCollectionId] });
}
const screenOf = n => { let p = n; while (p.parent && p.parent.id !== root.id) p = p.parent; return p.name; };
async function walk(n) {
  if (SKIP.test(n.name) || (n.type === 'VECTOR' && n.name.includes('-->'))) return;
  if (n.type === 'INSTANCE') {               // count it, never descend or read its own props
    const mc = await n.getMainComponentAsync();
    if (mc && !mc.remote) { const k = mc.parent && mc.parent.type === 'COMPONENT_SET' ? mc.parent.name : mc.name; (out.localComponents[k] ||= { count: 0, sample: n.id }).count++; }
    return;
  }
  out.scanned++;
  const t = n.type;
  if (n.parent && n.parent.id === root.id && t === 'FRAME') out.screens.push({ id: n.id, name: n.name });
  if (['FRAME','GROUP','COMPONENT'].includes(t)) {
    if (DEFAULT_NAME.test(n.name.trim()) && 'children' in n && n.children.length) out.defaultNames.push({ id: n.id, name: n.name, screen: screenOf(n), children: n.children.slice(0, 4).map(c => c.name) });
    else if (GENERIC_NAME.test(n.name.trim())) out.genericNames++;
  }
  if ('fills' in n && Array.isArray(n.fills)) {
    const bound = (n.boundVariables && n.boundVariables.fills) || [];
    n.fills.forEach((f, i) => {
      if (f.visible === false || f.type !== 'SOLID' || bound[i] || n.fillStyleId) return;
      const k = hex(f.color); (out.hardcodedFills[k] ||= { count: 0, samples: [] }).count++;
      if (out.hardcodedFills[k].samples.length < 4) out.hardcodedFills[k].samples.push({ id: n.id, name: n.name, screen: screenOf(n) });
    });
    for (const b of bound) if (b) { const info = await coll(b.id); const k = info.collection + ' :: ' + info.token; (out.boundColl[k] ||= 0); out.boundColl[k]++; }
  }
  if (n.layoutMode && n.layoutMode !== 'NONE') {
    const bv = n.boundVariables || {};
    for (const p of ['paddingLeft','paddingRight','paddingTop','paddingBottom','itemSpacing']) if (n[p] > 0 && !bv[p]) {
      const k = (p === 'itemSpacing' ? 'gap ' : 'padding ') + n[p];
      (out.spacing[k] ||= { count: 0, layers: [] }).count++;
      if (out.spacing[k].layers.length < 4 && !out.spacing[k].layers.includes(n.name)) out.spacing[k].layers.push(n.name);
    }
  }
  if (t === 'TEXT') {
    const sid = n.textStyleId; let issue = null;
    if (sid === figma.mixed) issue = 'mixed styles';
    else if (!sid) issue = 'no text style';
    else { const s = await figma.getStyleByIdAsync(sid); if (s && !s.remote) issue = 'local style: ' + s.name; }
    if (issue) { (out.text[issue] ||= { count: 0, samples: [] }).count++; if (out.text[issue].samples.length < 3) out.text[issue].samples.push({ id: n.id, chars: n.characters.slice(0, 40), screen: screenOf(n) }); }
  }
  if (t === 'FRAME' && n.detachedInfo) out.detached.push({ id: n.id, name: n.name, screen: screenOf(n) });
  if ('children' in n) for (const c of n.children) await walk(c);
}
await walk(root);
return out;
```
 
Text placed directly in the section, not inside a screen, is usually an annotation label. Check the `screen` value in the samples before reporting it.
 
## Report
 
Present the report as a page the designer can review, such as an HTML artifact or a Markdown file, depending on the environment.
 
1. **Header**: file (linked), page and section, screen and layer counts, platform, date, which collections were treated as semantic or primitive, spacing source of truth, breakpoints, and the previous report (or "baseline").
2. **Verdict**: Ready, Ready with fixes, or Not ready. Any blocker means Not ready. Add one sentence naming the blockers and what's clean.
3. **Counts** by severity.
4. **Findings** grouped by severity. Each finding gets a short title with the count, why it matters, a table of layers with node links (`https://www.figma.com/design/<fileKey>/?node-id=<id with - instead of :>`), and the suggested fix. In an interactive report, give each finding a checkbox.
5. **Not flagged and not scanned**: annotation layers ignored, and out-of-scope neighbours.
6. **Change summary for developers.**
Write in plain language without jargon. Lead with what to fix. Don't present a count as final until a second, targeted pass has confirmed it.
 
## Boundaries
 
- Don't modify the file. If the user asks for fixes, list exactly what would change and get a clear yes first. Renames are low risk; token swaps and component relinks change the design and need a visual check afterwards.
- Don't flag every layer in an icon, illustration or annotation.
- Don't invent tokens, breakpoints or naming rules. Ask, then suggest recording the answer in the context file.
- Don't scan the whole document when a page or section was given.
 
