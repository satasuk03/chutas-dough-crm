# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users
The baker/owner of Bröd Bread (single user), checking orders on phone and desktop — while planning bakes, coordinating pickups, and collecting payment.

## Product Purpose
A personal CRM for Bröd Bread's sourdough orders: one static HTML page listing every order with status, payment, delivery, and notes. Success = at a glance, know what to bake, what is due soon, and who still owes money.

## Operating Context
Single self-contained `index.html`, hosted as a static page (GitHub Pages) — no backend. Content is in Thai; customer names may be Thai or English.

The `ORDERS` array is **generated, not hand-edited**. Source of truth is the CSV set one level up (`../customers.csv`, `../orders.csv`, `../order-items.csv`, plus `short-name` in `../../products/brod-bread/*/*.md`); `../build-dashboard.py` rewrites the block between the `GENERATED FROM CSV` / `END GENERATED` sentinels. Everything outside those sentinels — markup, CSS, page logic — is hand-authored and safe to edit. The page is a **Bröd** board: only `brand = brod-bread` line items appear, while `total` carries the whole invoice so cross-brand orders can flag "รวมร้านอื่นด้วย".

This page is public. The `notes` column and customer `name` render verbatim, so contact details and addresses must stay in the private CRM notes, never in those fields.

## Capabilities and Constraints
- Order fields: id, ordered, due, name, status (inquiry|confirmed|making|delivered|cancelled), payment (unpaid|deposit|paid, `""` = free/compensation), delivery (pickup|delivery), shipping, items[], total, notes.
- Filters: status chips, search, payment, delivery method, product, due-date range; sortable table columns. The product dropdown is populated from the data at runtime, so a new menu item needs no markup change.
- **"ซ่อนที่ปิดแล้ว" is on by default** — the table opens showing only live work, hiding orders that are delivered *and* settled (paid or free) plus cancelled ones; the count line reports how many are hidden. Picking a delivered/cancelled status chip or a paid/free payment filter releases the switch automatically. Dashboard panels above the table always count every order.
- Mobile collapses the table into cards (≤760px).
- No runtime dependencies beyond Google Fonts; the deployed artifact must stay a single static file (plus the mascot image). The only tooling is the offline Python generator, which is stdlib-only and lives outside this repo.

## Brand Commitments
BRÖD design system (pinned by owner): retro two-color letterpress identity. Bakehouse Red `#C41D12`, Sky Blue `#5597CD`, Cream Paper `#F8EFEB`, Ink Brown `#2B1A15`, Soft Ink `#5B463E`, Blue Tint `#EEF5FB`. Unbounded for display, IBM Plex Sans for body/UI, IBM Plex Mono for labels. Thick 3–4px ink keylines, hard 8px offset shadows, halftone dots, diagonal stripes, sunburst rays, pills, dashed stamps. Mascot "Crumb" (`brod-mascot.png`): single-ink running girl, left → right, no recolor/drop-shadow/stretch, min 44px. Tagline: "Fresh bread, always running."

## Product Principles
- Glanceable first: the day's bakes, dues, and debts readable in seconds on a phone.
- Open on the open work: finished orders are history, not the default view — but never deleted, always one toggle away.
- One file, no infrastructure: data ships inside the page, which must never require a server.
- One source of truth: every figure on the page traces to a CSV row. If the page and the CSV disagree, the CSV wins and the page gets rebuilt.
- Two inks on cream, always — retro print charm without sacrificing legibility.
