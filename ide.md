---
title: "IDE Project Context"
---

# IDE Project Context

- Last updated: `2026-04-07`

## Project Snapshot
- Project name: `IDE Canada`
- Project type: WordPress site support / client guidance
- Reference page: `https://idecanada.org/initiatives/vision/`
- Task code prefix: `IDE`
- Priority: Medium
- Status: In Progress

## Current Task
- [x] IDE-01 Initiative Hero + brochure button support reply | Completed: 2026-03-25

## Client Request - 2026-03-24
- Client is trying to add a new page in the `Initiatives` area and needs help with two custom block behaviors.
- Block pattern in question: `Initiative Hero`
- Page in progress: `https://idecanada.org/initiatives/vision/`

### Item 1
- The circular image with the dotted outline at the top of the page needs to be updated.
- Client already tried changing the featured image, but that did not update the circular image.
- Working PM read: the image is likely controlled by a pattern field, post meta, or custom block setting rather than the standard featured image.

### Item 2
- The `Download Brochure (PDF)` block at the bottom is a custom button.
- Client can see a place to update the link, but is unsure where the PDF itself should be uploaded and how the button is expected to be updated.
- Working PM read: the reply likely needs to explain both the media-upload path and the custom field or block control that stores the final PDF URL.

## Output Goal
- Inspect or reason through how the `Initiative Hero` image is sourced.
- Confirm how the brochure PDF button is wired.
- Send the client a clear support reply with the exact update path for both items.

## Completion Note
- `IDE-01` was completed on `2026-03-25`.

## Estimate Note
- `1h` assumes this is a bounded support and investigation pass, not a code-change request.
- Add `1h` if the block pattern is misconfigured and turns into implementation instead of guidance.
