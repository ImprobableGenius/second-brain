---
title: "MASC Bundle Creation Definitions"
---

# MASC Bundle Creation Definitions

## Purpose
- Define how MASC work bundles should be broken into checklist notes.
- Keep bundle scopes small enough to schedule and complete cleanly.
- Keep bundle notes compatible with Quartz knowledge-garden linking and print export.

## Rules
- One bundle note should represent one focused work bundle.
- Target bundle size is about `5h to 6h`.
- If a bundle estimate grows past `6h`, split it into `A`, `B`, or more child bundles.
- Each bundle note should be named after the bundle itself.
- Each bundle note should have Quartz frontmatter with at least a `title`.
- Each bundle note should link back to [[masc/masc-board|MASC Board]].
- The corresponding bundle entry in [[masc/masc-board|MASC Board]] should link back to the bundle note, creating a bi-directional connection.
- Each bundle note should include a checklist, not only a prose description.
- Checklist items should be specific enough to complete or verify directly.
- Discussion-only items should still be kept inside the bundle note, but clearly labeled as discussion.
- Each bundle note should have a matching PDF generated with `pandoc`.

## Recommended Bundle Note Structure
- `Purpose`
- `Scope`
- `Checklist`
- `Discussion`
- `Dependencies`
- `Definition of Done`
- `Related Links`

## Checklist Rules
- Use one checkbox per concrete fix, review, or decision point.
- Prefer page- or component-specific wording over vague umbrella phrasing.
- Keep repeated signals if they materially reinforce urgency, but annotate them so duplication is intentional.
- Separate implementation tasks from discussion or ownership questions.

## Linking Rules
- Link to the board using Quartz wikilinks, for example:
  - `[[masc/masc-board|MASC Board]]`
- Link to related bundle notes where useful.
- Link to discussion notes when the bundle contains unresolved direction:
  - `[[masc/masc-discussion-points|MASC Discussion Points]]`

## Current Bundle Files
- [[masc/MASC-17A Print typography and spacing bundle|MASC-17A Print typography and spacing bundle]]
- [[masc/MASC-17B Print tables and controls bundle|MASC-17B Print tables and controls bundle]]
- [[masc/MASC-18 Lending detail and rendering polish bundle|MASC-18 Lending detail and rendering polish bundle]]
- [[masc/MASC-19 Calculator defects and feedback bundle|MASC-19 Calculator defects and feedback bundle]]
- [[masc/MASC-20A News archive remediation bundle|MASC-20A News archive remediation bundle]]
- [[masc/MASC-20B Knowledge Centre and video filter bundle|MASC-20B Knowledge Centre and video filter bundle]]
