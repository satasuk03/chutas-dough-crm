# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users
The baker/owner of Bröd Bread (single user), checking orders on phone and desktop — while planning bakes, coordinating pickups, and collecting payment.

## Product Purpose
A personal CRM for Bröd Bread's sourdough orders: one static HTML page listing every order with status, payment, delivery, and notes. Success = at a glance, know what to bake, what is due soon, and who still owes money.

## Operating Context
Single self-contained `index.html`, hosted as a static page (GitHub Pages). Order data is edited inline in the HTML source (the `ORDERS` array) and pushed — there is no backend. Content is in Thai; customer names may be Thai or English.

## Capabilities and Constraints
- Order fields: id, ordered, due, name, status (inquiry|confirmed|making|delivered|cancelled), payment (unpaid|deposit|paid|free), delivery (pickup|delivery), shipping, items[], total, notes.
- Filters: status chips, search, payment, delivery method, product, due-date range; sortable table columns.
- Mobile collapses the table into cards (≤760px).
- No build step, no dependencies beyond Google Fonts; must keep working as a single static file (plus the mascot image).

## Brand Commitments
BRÖD design system (pinned by owner): retro two-color letterpress identity. Bakehouse Red `#C41D12`, Sky Blue `#5597CD`, Cream Paper `#F8EFEB`, Ink Brown `#2B1A15`, Soft Ink `#5B463E`, Blue Tint `#EEF5FB`. Unbounded for display, IBM Plex Sans for body/UI, IBM Plex Mono for labels. Thick 3–4px ink keylines, hard 8px offset shadows, halftone dots, diagonal stripes, sunburst rays, pills, dashed stamps. Mascot "Crumb" (`brod-mascot.png`): single-ink running girl, left → right, no recolor/drop-shadow/stretch, min 44px. Tagline: "Fresh bread, always running."

## Product Principles
- Glanceable first: the day's bakes, dues, and debts readable in seconds on a phone.
- One file, no infrastructure: data lives in source, page must never require a server.
- Two inks on cream, always — retro print charm without sacrificing legibility.
