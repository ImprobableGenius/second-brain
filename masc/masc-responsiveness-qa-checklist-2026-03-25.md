# MASC Responsiveness QA Checklist - 2026-03-25

## Purpose
- Create a practical responsive QA walkthrough for the MASC theme based on the actual theme structure.
- Cover every major page family, reusable block, partial, and registered pattern.
- Use this as a working checklist for `MASC-05` planning and future remediation sequencing.

## Test Viewports
- `320x568` small mobile
- `375x812` modern mobile
- `390x844` larger mobile
- `768x1024` tablet portrait
- `1024x768` tablet landscape / small laptop
- `1280x800` desktop baseline
- `1440x900` wider desktop

## Global QA Rules
- Check for horizontal overflow at every viewport.
- Check heading wrap behavior and avoid orphaned single words where possible.
- Check image crops, masked shapes, and decorative SVGs for awkward clipping.
- Check CTA rows for wrapping, uneven heights, and collision with neighboring content.
- Check carousels, sliders, and tabs for swipe, arrow, dot, and overflow behavior.
- Check tables for overflow, clipping, cell wrapping, and readability on mobile.
- Check accordions and expandable content for touch targets and open/close spacing.
- Check breadcrumbs, search, filters, and pagination for wrap and truncation.
- Check footer and pre-footer spacing, especially where icons or logos stack.
- Check print-sensitive components only for layout leakage risk during responsive QA; print styling itself should stay in the print QA lane.

## Global Shell
- [ ] `header.php`: header layout, nav wrap, utility links, search trigger, language/secondary items, sticky behavior if present
- [ ] `footer.php`: footer columns, logo area, attribution spacing, legal links, newsletter/social spacing, mobile stacking
- [ ] `page.php`: generic page content width, Gutenberg content spacing, embedded media overflow
- [ ] `search.php`: search bar, results list, summary text, pagination, empty-state spacing
- [ ] Global page hero treatment across generic pages
- [ ] Breadcrumb spacing and wrapping on narrow screens

## Archive Templates
- [ ] `archive-factsheet.php`: hero, filters, cards/listing density, pagination, empty states
- [ ] `archive-knowledgecentre.php`: filters, cards, media metadata, pagination, search/filter stacking
- [ ] `archive-reports-publications.php`: filters, cards/list items, year/category metadata
- [ ] `archive-thematic-crop-maps.php`: FacetWP filters, info-card/coin layout, card media crop, taxonomy metadata wrapping
- [ ] `archive-yield-manitoba.php`: filter controls, cards, region/table interactions if present

## Single Templates
- [ ] `single-annual-report.php`: hero/title stack, document CTA area, content width
- [ ] `single-factsheet.php`: page hero, title order, quick links, tables, formulas, long content sections, print button placement leakage risk
- [ ] `single-thematic-crop-maps.php`: hero, metadata, content body, related content, image/legend behavior
- [ ] `single-yield-manitoba.php`: hero, content width, data presentation, CTA spacing

## Home And Landing Experiences
- [ ] `front-page.php`: full homepage flow from hero to footer
- [ ] Homepage hero block and supporting intro copy
- [ ] Homepage section transitions and vertical rhythm
- [ ] Resource / knowledge / news teaser sections on mobile and tablet
- [ ] Quick Links and card grids on home and overview pages
- [ ] Overview-page hero-image alignment where image crops were already flagged
- [ ] CTA wording wrap issues such as `View Land Parcel Info`

## Registered Custom Post Type Families
- [ ] `factsheet`
- [ ] `knowledgecentre`
- [ ] `reportsandpublications`
- [ ] `servicecentre`
- [ ] `thematiccropmaps`
- [ ] `yieldmanitoba`

## MASC Blocks
- [ ] `views/blocks/masc-calculator-frame`: widget stacking, embedded calculator width, CTA row wrap, mobile spacing
- [ ] `views/blocks/masc-callout-section`: heading/body/button balance, image alignment if present
- [ ] `views/blocks/masc-contact-banner`: copy wrapping, CTA/button spacing, icon alignment
- [ ] `views/blocks/masc-contact-map`: map embed height, card overlap, mobile stacking
- [ ] `views/blocks/masc-home-news`: card grid, thumbnails, category coin spacing, text truncation
- [ ] `views/blocks/masc-info-card`: icon/image, title, body, CTA wrap
- [ ] `views/blocks/masc-info-cards`: multi-card stacking, equal heights, mobile spacing
- [ ] `views/blocks/masc-knowledge-centre-carousel`: slide width, controls, swipe behavior, text truncation
- [ ] `views/blocks/masc-pdf-list`: long file names, button wrap, icon alignment
- [ ] `views/blocks/masc-quick-links`: icon circle sizing, label wrap, row/column transitions
- [ ] `views/blocks/masc-resource-carousel`: slide widths, nav controls, mobile margins
- [ ] `views/blocks/masc-service-centres`: map/list balance, card density, location metadata wrap
- [ ] `views/blocks/masc-social-media`: icon row wrap, feed/card spacing
- [ ] `views/blocks/masc-thematic-crop-cards`: card grid, taxonomy coin wrap, image crop, CTA spacing
- [ ] `views/blocks/masc-video-carousel`: thumbnail crops, play affordances, title/description truncation
- [ ] `views/blocks/masc-yield-manitoba-cards`: card layout, metadata wrap, CTA line length

## Shared / Starter Blocks
- [ ] `views/blocks/accordion`: touch targets, icon alignment, open-state spacing
- [ ] `views/blocks/button`: button height, long-label wrap, icon alignment if present
- [ ] `views/blocks/buttons`: multi-button wrap and spacing
- [ ] `views/blocks/grid`: column collapse behavior
- [ ] `views/blocks/grid-cell`: internal spacing consistency
- [ ] `views/blocks/homepage-hero`: heading scale, body width, image/mask behavior
- [ ] `views/blocks/media-text`: mobile reflow, image crop, text spacing
- [ ] `views/blocks/media-text-innerblocks`: nested content spacing
- [ ] `views/blocks/page-children`: card grid and CTA wrap
- [ ] `views/blocks/section`: section padding and nested layout consistency
- [ ] `views/blocks/sitemap`: hierarchy spacing and column collapse
- [ ] `views/blocks/sitemap-post-list`: long-title wrapping and list spacing

## Partials / Reused Components
- [ ] `views/partials/category-coin.php`: long label wrap, pill height, icon alignment
- [ ] `views/partials/facets-controls-section.php`: filter wrap, spacing, active-state visibility
- [ ] `views/partials/facetwp-search-box.php`: input width, placeholder visibility, mobile button alignment
- [ ] `views/partials/hero-intro.php`: intro width and heading/body rhythm
- [ ] `views/partials/info-card.php`: text truncation, CTA wrap, icon/image balance
- [ ] `views/partials/knowledge-centre-card.php`: thumbnail crop, metadata wrap, card height consistency
- [ ] `views/partials/page-hero-factsheet.php`: title, subtitle, print button, quick-link placement
- [ ] `views/partials/page-hero.php`: heading/image composition, spacing, CTA wrap
- [ ] `views/partials/pagination.php`: narrow-screen wrap and touch target size
- [ ] `views/partials/product-card.php`: card density, button wrap, image crop
- [ ] `views/partials/program-overview-hero.php`: hero copy/image balance, alignment, crop behavior
- [ ] `views/partials/service-card.php`: icon/image size, copy wrap, CTA spacing
- [ ] `views/partials/social-media.php`: icon sizing, multi-column collapse, caption wrap

## Patterns
- [ ] `patterns/example-split.php`
- [ ] `patterns/example-split-2.php`
- [ ] `patterns/factsheet-cards-1col.php`
- [ ] `patterns/factsheet-cards-2col.php`
- [ ] `patterns/factsheet-cards-3col.php`
- [ ] `patterns/factsheet-cards-4col.php`
- [ ] `patterns/info-cards-2x2.php`
- [ ] `patterns/info-cards-3-cols.php`
- [ ] `patterns/info-cards-4-cols.php`
- [ ] `patterns/matrix-crop-frequency.php`
- [ ] `patterns/matrix-crop-performance.php`
- [ ] `patterns/media-text.php`
- [ ] `patterns/product-card-row-2.php`
- [ ] `patterns/product-card-row-3.php`
- [ ] `patterns/product-card-row-5.php`
- [ ] `patterns/table-basic.php`
- [ ] `patterns/table-heading.php`
- [ ] `patterns/table-special-column.php`
- [ ] `patterns/table-style-row.php`
- [ ] `patterns/table-total.php`

## High-Risk Responsive Areas To Prioritize
- [ ] Homepage hero, post-hero, footer, and resource/news sections
- [ ] Overview heroes with image alignment sensitivity
- [ ] Calculator-frame pages and embedded widgets
- [ ] Factsheet hero + quick-links + print-button layout
- [ ] Long-form factsheet tables and formula examples
- [ ] Search results cards and auto-generated summary areas
- [ ] Carousels across resources, videos, and knowledge centre
- [ ] Thematic crop map cards and taxonomy coin wraps

## Execution Order Recommendation
1. Global shell and homepage
2. Overview pages and calculator-frame pages
3. Factsheet template family
4. Archive templates
5. Single templates
6. Shared blocks and partials
7. Patterns

## Notes
- This is a structure-based QA checklist, not a final bug list.
- Use it to collect actual responsive findings into a second document or tracker lane.
- For MASC, the highest-yield approach is still to solve repeated responsive issues systemically where possible rather than page by page.
