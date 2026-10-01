# Design system context: blank template

This file is blank on purpose. Copy it into this same `references/` folder, rename it to match a real product (for example `acme-design-system-context.md`), and fill it in. The filled-in version will contain real organizational detail, so keep it out of any repo you don't fully control. The repo's `.gitignore` already excludes `*-context.md` files in this folder.

The handoff check reads a filled-in version before scanning, so it doesn't have to ask these questions every time. When a run turns up a new answer, add it here.

## Product and platforms

- Product: _name_
- Platforms or surfaces this file covers: _e.g. patient web app, provider web app, iOS app_
- Design system name and the Figma library that is the source of truth: _name and version_

## Breakpoints

List the breakpoints every screen should have, per platform. Write "desktop only" if that's the current scope, and the date you confirmed it.

| Platform | Breakpoints | Confirmed |
| --- | --- | --- |
| _platform_ | _e.g. 1280, 768, 375_ | _date_ |

## Token collections

Which Figma variable collections are semantic (correct to bind to) and which are primitive (should not be bound directly)?

- Semantic: _e.g. "Colour mode", "Theme"_
- Primitive: _e.g. "Palette", "Core"_

## Spacing source of truth

- Library and collection: _e.g. Design System v1.1, "Spacing" collection_
- Tokens it includes: _list them, or describe the scale_
- Known gaps: _e.g. "only card padding tokens exist; general layout spacing is unbound by design"_

## Naming conventions

- Screen names: _e.g. `Platform / Flow / Screen / State`_
- Layer and component names: _e.g. PascalCase for sections and components_

## Annotation components to skip

Names of annotation components your team places on the canvas, so the scan can ignore them: _e.g. "Annotation Header", "Sticky Note", "Dev annotation"_
