---
title: "Encore Cabinets Project Context"
---

# Encore Cabinets Project Context

- Last updated: `2026-04-07`

## Snapshot
- Project type: WooCommerce ecommerce storefront
- Local repo: `/Users/aarongilani/Local Sites/elite/app/public/wp-content/themes/elite`
- Repo remote: `git@github.com:Vincent-Design-Inc/elite-cabinets.git`
- Active branch: `main`
- Load: Medium
- Working estimate: 6h discovery
- Task code prefix: `ENCR`
- Priority: Medium
- Start date: TBD
- Deadline: Capacity Available
- Status: Capacity queue

## Current Task
- [ ] ENCR-01 Zonos recommendation | Estimate: 6h | Trigger: when capacity is available | Flag: High Uncertainty

## Current Blocker
- U.S. shipment clarification is still pending.
- The related marketing campaign is blocked until the U.S. shipping direction is confirmed.

## Recommendation Snapshot
- Recommended phase 1 path: use the official Zonos Checkout for WooCommerce extension for U.S.-destination orders only.
- Use a dedicated international checkout button first instead of replacing the existing WooCommerce checkout button globally.
- Keep the current Canadian checkout and Authorize.net flow in place while routing U.S. cross-border orders through Zonos.
- Treat the recommendation as discovery-only for now. Full implementation should be estimated separately after checkout, shipping-carrier, and catalog-mapping decisions are confirmed.

## Platform Notes
- Sage/Acorn-based custom WordPress theme with extensive WooCommerce templates and storefront overrides.
- Theme `README.md` documents a WPE staging flow from `main`, with production promotion handled from WPE.
- Documented WordPress dependencies include ACF Pro, WooCommerce, an Authorize.net gateway extension, and Olark.
- Installed ecommerce-related plugins include `woocommerce`, `woocommerce-direct-checkout`, `woocommerce-multi-currency`, `price-by-country`, `woocommerce-payments`, `woocommerce-gateway-authorize-net-cim`, `payment-gateway-authorizenet-woocommerce`, and multiple YITH merchandising/search plugins.
- The theme worktree is dirty, with active edits in checkout styles, cabinet customization UI, featured products, and WooCommerce email templates.

## Checkout Constraints
- `app/Controllers/PaymentPortal.php` swaps between U.S. and Canadian Authorize.net gateways based on the shopper shipping country.
- `app/Controllers/ProductPropertyListener.php` persists custom cabinet configuration selections and other cart metadata using keys like `customization_option_*`.
- The theme overrides WooCommerce cart and checkout templates, so button interception and checkout redirection must be tested against Elite's markup rather than stock WooCommerce templates.
- Existing country-pricing and currency plugins may overlap with Zonos localization, pricing, or shopper-routing behavior.

## Why This Recommendation Fits
- Zonos documents a maintained WooCommerce checkout extension with test mode, shipping zones, mapping settings, and order import, which is a safer path than a custom API build for this codebase.
- A dedicated international checkout button limits regression risk in a heavily customized checkout and preserves the current domestic flow while the U.S. lane is validated.
- Zonos explicitly supports mapping WooCommerce product attributes and custom metadata, which matters because Elite passes cabinet customization data into cart items.
- Zonos also changes operations for international orders: payment is collected in Zonos Checkout, refunds and cancellations are handled in Dashboard, and labels are expected to be printed from Dashboard unless separately certified.

## Delivery Plan
- Audit the current WooCommerce checkout, country-based gateway, and cart metadata flow: 2h
- Review Zonos WooCommerce extension setup and required mapping against Elite's stack: 2h
- Produce the recommendation, rollout shape, and risk register for U.S. shipping: 2h
- Provisional implementation budget if approved: 20h to 28h, depending on cart metadata mapping, multi-currency overlap, and production QA scope.

## PM Risks / Open Questions
- Unknown whether the business wants Zonos to own the full U.S. checkout and payment flow or only provide shipping and landed-cost visibility.
- Unknown which carrier account and service levels should be used for the U.S. zone in Zonos.
- Need confirmation whether U.S. is the only target market or just phase 1 of broader cross-border rollout.

## Source Links
- [Zonos WooCommerce Checkout integration guide](https://zonos.com/docs/global-ecommerce/integration/integrating-new-checkout/woocommerce)
- [Zonos WooCommerce product attribute mapping guide](https://zonos.com/docs/global-ecommerce/integration/integrating-new-checkout/woocommerce/map-woocommerce-product-attributes)

## Notes
- Original project shell came from `Workload Metrics - Main.csv`.
