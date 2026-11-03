# ShopIt desktop: rules for page builders (Ujyalo Pasal v1.0)

> **⚠ IMAGE URLS:** do **not** use `https://api.shopitnepal.com/uploads/...` in `<img src>`. That host sends `Cross-Origin-Resource-Policy: same-site`, so the images render **broken** in Chrome and other browsers outside shopitnepal.com. Rewrite the prefix to **`https://www.shopitnepal.com/files/uploads/...`**. It serves the same file, returns 200, and has no CORP header (verified 2026-11-02). Example: `https://www.shopitnepal.com/files/uploads/image/cApzZcdownload-remov.webp`. Logo and banner URLs on `www.shopitnepal.com` are fine as listed.

Start every page from `_shell.html`. Paste its `<head>` links and its whole `<style>` block verbatim, keep the header and footer markup verbatim, and put page-only CSS in a **second** `<style>` block that uses tokens only. Component reference: `00-design-system.html`. Images come from `UX/assets/manifest.md` as absolute `https://` URLs.

## Frame and grid
- Frame `body` is **1440px** wide; height follows the content. No horizontal scroll.
- `.container` is **1280px**, centred (80px side margins), with **12 columns of 85.33px and 24px gutters**.
  - Grocery product grid: 5 × `.product-card` (232px) with 30px gaps, or 4-up for wider cards. Use `display:grid; grid-template-columns:repeat(5,232px); justify-content:space-between`.
  - Meal grid: 4 × `.meal-card` (296px) with 32px gaps.
  - Product detail: 7 cols for media and 5 cols for the buy box (≈ 736 + 520).
  - Cart/checkout: 8 cols for items, 4 cols for a sticky-looking summary (≈ 848 + 408). Do not use `position:sticky` or `fixed`.
- Spacing scale: 4, 8, 12, 16, 20, 24, 32, 40, 48, 64, 80, 96 (`--s-*`). Nothing off-scale.
- Vertical rhythm: `.section` gives a **64px** gap between sections. The gap from a section head to its content is 24px. Inside cards, use 12–16px.
- Radius: cards 20, inputs 14, image tiles 14, buttons and chips pill. Hero blocks may use `--r-xl` (28).
- Layout must use flex or grid in normal flow. `position:absolute` is allowed **only** for small badges already in the system (deal tag, fav heart, cart count, cooking chip). No transforms and no JS.

## Colour rules
- **Amber `--primary` is a fill, never text on light.** Amber text uses `--primary-ink` (#B35F00). Text on an amber fill is cocoa (`--on-primary`), never white.
- **Pink `--accent` is for deals only**: `.tag-deal`, the "Flash deal" CTA and price-drop numbers. Never use it for errors or decoration.
- Cocoa `--secondary` is for selected chips, the active nav, the search button and dark bands such as the header strip and footer.
- Green `--success` is for ETA/live states and "fresh". Orange `--warning` is for "cooking now", delays and form errors.
- Logo green (#02A235) lives inside the logo only. Do not use it as a UI colour.
- Page background `--bg` (cream). Cards `--surface` (white). Image wells `--surface-sunk`.

## Typography
- Display and headings: **Baloo 2** 700/800. Body and UI: **Mukta** 400–700. Both fonts render Devanagari natively.
- Scale: display-xl 64/68 (home hero only), display-l 48/54, h1 36/42, h2 28/34 (section titles use 32/38 via `.section-head h2`), h3 22/28, h4 18/24, body-l 18/28, body 16/24, small 14/20, micro 12/16.
- One display-xl per page at most. Section titles are always `.section-head` with a Nepali or Romanized kicker above an English title.

## Which component for what
| Need | Use |
|---|---|
| Main CTA (Add to cart, Place order, Confirm location) | `.btn.btn-primary` (`.btn-lg` on PDP and checkout). Use one primary per view area. |
| Secondary action | `.btn-secondary` (cocoa) or `.btn-outline`. Text links use `.btn-ghost` / `.see-all`. |
| Deal or flash sale CTA | `.btn-deal` (rare) |
| Help | `.btn-whatsapp` "WhatsApp us" (+977 971-2023010) |
| Grocery item | `.product-card`: ETA line, name, size, price now/was, `.btn-add` or `.stepper` once in the cart |
| Cloud-kitchen dish | `.meal-card`: veg/non-veg mark, portion, `.spice` meter, `.chip-cooking` "Cooking now · 20–30 min" |
| Delivery promise | `.chip.chip-eta` with `.live-dot`. **Always a range** ("8–14 min"), never a single number. |
| Age-restricted (Liquors, Wellness) | `.chip-age` "**18+** · ID at door", which is calm and grey. Never show these on the hero or near Baby. |
| Discount | `.tag-deal` "-10%" (show a real % only, with the struck MRP in `.price-was`) |
| Merch sticker | `.tag-sticker` ("Bestseller", "Ramro choice") – max one per card |
| Filters / facets | `.chip` / `.chip-selected` |
| Forms | `.field` > `.field-label` + `.input` + `.field-help`. Phone uses `.input-prefix` "+977". Landmark uses `.input.textarea`. |
| Payment choice | `.radio-card` list. **Cash on delivery first and pre-selected**, then eSewa, then Khalti. |
| Money moments (cart, checkout, PDP buy box) | `.trust-rail` (COD lead item, wallets, VAT/PAN bill, WhatsApp) + `.legal-line` with the reg. no. |
| Free-delivery nudge | `.progress` ("Rs. 155 more for free delivery") |
| Feedback | `.toast` success/info/warning/error, shown static at the top-right of the content area in mocks |

## Voice and microcopy (English UI, Nepali touches)
Functional labels (buttons, form labels, prices, legal) are **always English**. Nepali appears in kickers, greetings, empty states and celebration moments: Romanized in Mukta, or Devanagari via `.np`. The tone is a friendly dai/didi: short, warm and never judging.
- Search hint: "Ke chahiyo aaja? Try “chicken momo”". Rotate the hint: "Wai Wai", "MamyPoko pants", "Coke Zero", "Buff Choila".
- Location: "Delivery in 8–14 min · Sitapaila, Nagarjun-4" and "Add a landmark (e.g. opposite Ganesh Mandir)"
- Section kickers: "आजको लागि" (for today) · "Bhok lagyo?" · "Taaja aaja" · "Pheri kinnus" (buy again)
- Add-on: "Ramro choice! Add a Coke Zero for Rs. 35?"
- Free delivery: "Rs. 155 more for free delivery. Almost there!"
- Tracking: "Rider on the way, 6–9 min. Kalanki chowk pugyo."
- Delay (honest): "Rain near Kalanki. Adding 4–6 min, sorry!"
- Checkout trust: "Pay at your door. Cash on delivery is fine."
- Empty cart: "Khali chha! Your cart is empty. Start with today's momo?"
- Success: "Order placed! Dhanyabad 🙏"
- 18+: "18+ · ID check at your door. Delivered in a plain bag." (calm and factual, no warnings in red)
- Correct the product spellings from the site: **Paneer** (not Panner), **Buff Choila**, **Mutton Choila**, **Momo**.

## Midnight mode (Raati Rush skin)
- **When:** only screens set between **22:00 and 04:00**, the Midnight Cravings shelf/landing, and any "late-night" scenario. Everything else is Ujyalo Pasal.
- **How:** add `class="theme-midnight"` to `<body>` for a full page, or to a wrapper `<section>` for a dark Midnight Cravings band on a daytime page. That is the only switch. Do not hand-pick night colours; the semantic tokens swap automatically (volt `--primary`, violet `--secondary`, deep-night `--bg`).
- Fonts stay Baloo 2 + Mukta. Only the palette changes.
- The header logo automatically gets a cream tile in Midnight, because the logo's wordmark is dark.
- Copy can be cheekier: "Bhok lagyo? 1am ma pani khulla 🌙", "Momo incoming. 20–30 min."

## Canonical numbers (use on ALL pages)
| Value | Canonical |
|---|---|
| Delivery fee | **Rs. 49** |
| Free delivery | on baskets **over Rs. 1,500**. Compute "Rs. X more for free delivery" as 1,500 − basket subtotal, then fee = Rs. 0 once over. |
| Daytime grocery ETA | **8–14 min** |
| Midnight (22:00–04:00) grocery ETA | **9–15 min** |
| Hot food (cloud kitchen) | **20–30 min** (cook + ride) |
Live in-progress states (e.g. "Rider 6–9 min away") and honest delay messages may show other ranges. Product and add-on prices come from the manifest and are not affected.

## Data to use
Use real products and prices from `UX/assets/manifest.md` (e.g. Chicken Steam Momo Rs. 270 / MRP 300, Paneer Biryani Rs. 450 / 500, Coke Zero 250ml Rs. 35). Places: Sitapaila, Nagarjun-4, Kalanki, Balaju, Swayambhu. WhatsApp: +977 971-2023010. Company: Shopit Nepal Pvt. Ltd., Reg. no. 376790/82/83. PAN is a placeholder `60XXXXXXX`.
