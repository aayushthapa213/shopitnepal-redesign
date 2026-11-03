# ShopIt Nepal asset manifest

> **Use `www.shopitnepal.com/files/uploads/...` URLs, not `api.shopitnepal.com`.** The API host sends `Cross-Origin-Resource-Policy: same-site`, so browsers (and html-to-figma) block its images when loaded from another origin. The storefront proxies the same files at `https://www.shopitnepal.com/files/uploads/<path>` without that restriction, and every URL below uses that form.

Harvested 2026-11-02 from https://www.shopitnepal.com/ (site pages + its public JSON API `https://api.shopitnepal.com/api/mobile/...`).
Every URL below was fetched and returned **HTTP 200 with an image/* content type** (64/64 OK).

## How images are served
- Product/category images live at `https://www.shopitnepal.com/files/uploads/...` (absolute URLs below, use these in `<img src>`).
- The storefront also proxies them as `https://www.shopitnepal.com/files/uploads/image/<file>` and wraps them with Next.js `/_next/image?url=<encoded source>&w=640&q=75`. The "image URL" column is always the underlying source, not the `/_next/image` wrapper.
- Product photos are mostly cut-out (transparent/white background) packshots; paths are relative in the API (`uploads/...`), prefixed with `https://api.shopitnepal.com/` here.
- Local paths are relative to the project root (`C:UsersStudentshopit_UI`); from `UX/desktop/*.html` use `../assets/<file>`.

## Excluded on purpose
Age-restricted categories (Smokes, Sexual Wellness) were not harvested. Liquors are included (2 items) but are age-restricted: show only behind an age gate / avoid on hero surfaces.

## Logo
| Use | Image URL | Local file |
|---|---|---|
| Header logo (green, transparent) | https://www.shopitnepal.com/logo/svg/GreenLogoTransaprant.svg | UX/assets/logo-header-green.svg |
| Footer logo | https://www.shopitnepal.com/footer-logo.svg | UX/assets/logo-footer.svg |
| Favicon 512 (app icon) | https://www.shopitnepal.com/favicon/android-chrome-512x512.png | UX/assets/app-icon-512.png |
| Apple touch icon | https://www.shopitnepal.com/favicon/apple-touch-icon.png | UX/assets/apple-touch-icon.png |
| Favicon 32 | https://www.shopitnepal.com/favicon/favicon-32x32.png | UX/assets/favicon-32.png |
| OG share image | https://www.shopitnepal.com/favicons/og/og-shopit-homepage.png | UX/assets/og-share.png |
| Spinwheel icon | https://www.shopitnepal.com/spinwheeloriginal.svg | UX/assets/icon-spinwheel.svg |

Notes: primary mark = green wordmark SVG (header uses it at ~h-10, scaled 1.5×). Footer logo is a separate SVG (check contrast on dark backgrounds). No white/dark variant exists on the site beyond the footer logo. App download link: https://downloadapp.shopit.com.np/ (the site shows a green "Download Our App" button; **no App Store / Google Play badge images were found** — design placeholder badges).

## Banners (homepage hero carousel)
| Alt/name | Image URL | Local file |
|---|---|---|
| Spin Wheel | https://www.shopitnepal.com/files/uploads/image/kFJCBBframe-473.webp?v=s149-2026-05-24 | UX/assets/banner-spin-wheel.webp |
| Everything at one place | https://www.shopitnepal.com/files/uploads/image/qCDA6mframe-111.webp?v=s149-2026-05-24 | UX/assets/banner-everything-one-place.webp |
| Midnight Cravings | https://www.shopitnepal.com/files/uploads/image/midnight-cravings-2026-06.webp?v=s149-2026-05-24 | UX/assets/banner-midnight-cravings.webp |
| Drinks | https://www.shopitnepal.com/files/uploads/image/3fDczJframe-111-1.webp?v=s149-2026-05-24 | UX/assets/banner-drinks.webp |

## Categories
Tile images are PNG/WebP icons; `baseColor` is the tile background tint from the API.

| Category | Tile color | Image URL | Local file | Category URL |
|---|---|---|---|---|
| Baby Products | #E5EFFF | https://www.shopitnepal.com/files/uploads/image/4923ac15-f8d3-4a7a-93ea-ff23212603f7-tile.png | UX/assets/cat-baby-products.png | https://www.shopitnepal.com/products?category=4923ac15-f8d3-4a7a-93ea-ff23212603f7 |
| Chocolates | #E1E1FF | https://www.shopitnepal.com/files/uploads/image/3cfa4026-c894-46ee-9ea6-1ce34e9955cf-tile.png | UX/assets/cat-chocolates.png | https://www.shopitnepal.com/products?category=3cfa4026-c894-46ee-9ea6-1ce34e9955cf |
| Cloud Kitchen | #E5EFFF | https://www.shopitnepal.com/files/uploads/image/60dec028-21fe-471f-8288-b3ee1d6ddb03-tile.png | UX/assets/cat-cloud-kitchen.png | https://www.shopitnepal.com/products?category=60dec028-21fe-471f-8288-b3ee1d6ddb03 |
| Daily Groceries | #FCE4EC | https://www.shopitnepal.com/files/uploads/image/06e00eef-d294-429c-a8be-6fe2987a47dc-tile.png | UX/assets/cat-daily-groceries.png | https://www.shopitnepal.com/products?category=06e00eef-d294-429c-a8be-6fe2987a47dc |
| Dairy Products | #E5EFFF | https://www.shopitnepal.com/files/uploads/image/38sZ9Swatermarked-im.webp | UX/assets/cat-dairy-products.webp | https://www.shopitnepal.com/products?category=01a03793-d9b8-70fe-a3fe-b6de9323ccb0 |
| Hajmola | #E5EFFF | https://www.shopitnepal.com/files/uploads/image/019e48af-62b2-76aa-ae7e-b8ede6f549f2-tile.png | UX/assets/cat-hajmola.png | https://www.shopitnepal.com/products?category=019e48af-62b2-76aa-ae7e-b8ede6f549f2 |
| Home & Kitchen | #E5EFFF | https://www.shopitnepal.com/files/uploads/image/693c5160-bba7-4e14-b647-7336390b5d86-tile.png | UX/assets/cat-home-and-kitchen.png | https://www.shopitnepal.com/products?category=693c5160-bba7-4e14-b647-7336390b5d86 |
| Home & Living | #E5EFFF | https://www.shopitnepal.com/files/uploads/image/019da1bb-e06a-7289-9d2b-5f8468319aa2-tile.png | UX/assets/cat-home-and-living.png | https://www.shopitnepal.com/products?category=019da1bb-e06a-7289-9d2b-5f8468319aa2 |
| Ice Creams | #E5EFFF | https://www.shopitnepal.com/files/uploads/image/019e6d95-0a92-747b-9a56-fb45dbf146e8-tile.png | UX/assets/cat-ice-creams.png | https://www.shopitnepal.com/products?category=019e6d95-0a92-747b-9a56-fb45dbf146e8 |
| Liquors | #E8E8E8 | https://www.shopitnepal.com/files/uploads/image/839de095-a38e-4d59-90f9-0be22db80fcc-tile.png | UX/assets/cat-liquors.png | https://www.shopitnepal.com/products?category=839de095-a38e-4d59-90f9-0be22db80fcc |
| Packaged Foods | #FFF8E1 | https://www.shopitnepal.com/files/uploads/image/3c43d4a6-2499-45e9-b99b-d43e7c27fa20-tile.png | UX/assets/cat-packaged-foods.png | https://www.shopitnepal.com/products?category=3c43d4a6-2499-45e9-b99b-d43e7c27fa20 |
| Party Supplies | #E5EFFF | https://www.shopitnepal.com/files/uploads/image/a16c3015-14c2-449c-af71-18a8318ad38c-tile.png | UX/assets/cat-party-supplies.png | https://www.shopitnepal.com/products?category=a16c3015-14c2-449c-af71-18a8318ad38c |
| Personal Care | #E5EFFF | https://www.shopitnepal.com/files/uploads/image/6f86a013-b009-451e-8d96-9cc0a7ad372b-tile.png | UX/assets/cat-personal-care.png | https://www.shopitnepal.com/products?category=6f86a013-b009-451e-8d96-9cc0a7ad372b |
| Soft Drinks | #FFFEE9 | https://www.shopitnepal.com/files/uploads/image/0fe20f47-3646-42a9-9c35-3409a55de164-tile.png | UX/assets/cat-soft-drinks.png | https://www.shopitnepal.com/products?category=0fe20f47-3646-42a9-9c35-3409a55de164 |

## Products
Prices are current `price` in Rs.; MRP shown when higher. "Orig" notes the site's original spelling where fixed. Cloud Kitchen items are made-to-order.

| Name | Category | Price (Rs.) | Image URL | Local file | Product URL |
|---|---|---|---|---|---|
| Baby Sensitive Wipes 80 sheets | Baby Products | 140 (MRP 150) | https://www.shopitnepal.com/files/uploads/image/BecFg778934-jpg-remo.webp | UX/assets/p-baby-product-baby-sensitive-wipes-80-sheets.webp | https://www.shopitnepal.com/products/fe7fdf4b-35a6-402a-964c-a27c78845589 |
| GCG Baby Wipes Aloe and Chamomile 90 pcs | Baby Products | 160 (MRP 170) | https://www.shopitnepal.com/files/uploads/image/xD6FxP78922-jpg-remo.webp | UX/assets/p-baby-product-gcg-baby-wipes-aloe-and-chamomile-90-pcs.webp | https://www.shopitnepal.com/products/f8699212-f785-4af9-84ed-fb6a1788971b |
| White Rabbit 108g | Chocolates | 240 (MRP 270) | https://www.shopitnepal.com/files/uploads/image/q3BBh9b2351fdab3e1ef.webp | UX/assets/p-chocolates-white-rabbit-108g.webp | https://www.shopitnepal.com/products/445384d3-060a-49a7-8557-31ec51d13a82 |
| Sunfeast Choco Roll 120g | Chocolates | 145 (MRP 150) | https://www.shopitnepal.com/files/uploads/image/5yM86V52965496522557.webp | UX/assets/p-chocolates-sunfeast-choco-roll-120g.webp | https://www.shopitnepal.com/products/83655324-248b-49bf-be4c-f471e67f1353 |
| Paneer Biryani | Cloud Kitchen | 450 (MRP 500) | https://www.shopitnepal.com/files/uploads/image/ff229b1b-6de3-49cd-a8be-c2f8181c76b6-s249nobg.png | UX/assets/p-cloud-kitche-paneer-biryani.png | https://www.shopitnepal.com/products/eef5075c-a815-48df-95ce-eddcb09a81de |
| Mix Fried Rice | Cloud Kitchen | 350 (MRP 400) | https://www.shopitnepal.com/files/uploads/image/56bc2fa0-54cb-48fd-a22b-715b3e229f0b-s249nobg.png | UX/assets/p-cloud-kitche-mix-fried-rice.png | https://www.shopitnepal.com/products/1126102c-af7d-4e4b-a880-23214c57fb4b |
| Paneer Wrap | Cloud Kitchen | 349 (MRP 400) | https://www.shopitnepal.com/files/uploads/image/5200e039-eec3-4094-8cfe-e709770868b6-s249nobg.png | UX/assets/p-cloud-kitche-paneer-wrap.png | https://www.shopitnepal.com/products/c1bd6a3b-6ea1-460b-a6db-98e4fe27a146 |
| Chicken Wrap | Cloud Kitchen | 349 (MRP 400) | https://www.shopitnepal.com/files/uploads/image/h8q9Pskorean-chicken.webp | UX/assets/p-cloud-kitche-chicken-wrap.webp | https://www.shopitnepal.com/products/017e8ca9-f470-40d3-94f2-a16727d31a56 |
| Chicken Timur Sadheko | Cloud Kitchen | 450 (MRP 500) | https://www.shopitnepal.com/files/uploads/image/49ad5328-46c1-4285-ad11-3c54ae085e3d-s249nobg.png | UX/assets/p-cloud-kitche-chicken-timur-sadheko.png | https://www.shopitnepal.com/products/92cfd980-5ffa-4706-93fa-5ada023ff483 |
| Buff Choila _(orig: BUff Choila)_ | Cloud Kitchen | 450 (MRP 500) | https://www.shopitnepal.com/files/uploads/image/880d0cb9-0d77-4229-8695-91e64a399255-s249nobg.png | UX/assets/p-cloud-kitche-buff-choila.png | https://www.shopitnepal.com/products/500b5ced-7906-4b67-bf13-68fe13dea963 |
| Mutton Choila _(orig: Mutton Cholia)_ | Cloud Kitchen | 600 (MRP 675) | https://www.shopitnepal.com/files/uploads/image/367982de-6d11-4b67-b454-fb7186601def-s249nobg.png | UX/assets/p-cloud-kitche-mutton-cholia.png | https://www.shopitnepal.com/products/1773ca11-e2f7-4664-becb-02cdebe052d8 |
| Chicken Choila | Cloud Kitchen | 450 (MRP 500) | https://www.shopitnepal.com/files/uploads/image/7e0d08cc-d0df-49ca-a073-b4749d91465f-s249nobg.png | UX/assets/p-cloud-kitche-chicken-choila.png | https://www.shopitnepal.com/products/6dfdcb6d-397a-4c47-9f38-25cfb5dcf2a7 |
| Mac Cereal Instant Cereal Beverage | Daily Groceries | 550 (MRP 585) | https://www.shopitnepal.com/files/uploads/images/products/mac-cer-ins-bevwcbza2.webp | UX/assets/p-daily-grocer-mac-cereal-instant-cereal-beverage.webp | https://www.shopitnepal.com/products/748d928a-13e9-4cdb-842c-4f86ff75d32c |
| NGPL Premium Long Grain Basmati Rice 20kg | Daily Groceries | 3750 (MRP 4200) | https://www.shopitnepal.com/files/uploads/image/pyDkWgd6fe7d56-845a-.webp | UX/assets/p-daily-grocer-ngpl-premium-long-grain-basmati-rice-20k.webp | https://www.shopitnepal.com/products/3cd64c2a-66a1-4011-8afe-daef593d5297 |
| Stella Bathroom Freshener Pocket Orange Sunkist 10g | Home & Kitchen | 110 (MRP 120) | https://www.shopitnepal.com/files/uploads/image/KuARVeimages-2026-09.webp | UX/assets/p-home-and-kit-stella-bathroom-freshener-pocket-orange-.webp | https://www.shopitnepal.com/products/d1b57bfb-5ca0-4ef3-94dd-a0d08836e8ef |
| Bennevis Strawberry Cheesecake 500ml | Ice Creams | 545 (MRP 550) | https://www.shopitnepal.com/files/uploads/image/hXHwgj085a72bd-d7c1-.webp | UX/assets/p-ice-creams-bennevis-strawberry-cheesecake-500ml.webp | https://www.shopitnepal.com/products/18d77c4f-8858-417e-85ec-65f4df409805 |
| Nova 21 Love ice Cream 500ml | Ice Creams | 265 (MRP 270) | https://www.shopitnepal.com/files/uploads/image/fbpNJ4img20260529084.webp | UX/assets/p-ice-creams-nova-21-love-ice-cream-500ml.webp | https://www.shopitnepal.com/products/27e2850c-8eeb-4cf1-8ea5-e11cc07290a2 |
| Barahsinghe Pilsner Beer 650ml | Liquors | 440 (MRP 455) | https://www.shopitnepal.com/files/uploads/images/products/bar-650mlieHBi6.webp | UX/assets/p-liquors-barahsinghe-pilsner-beer-650ml.webp | https://www.shopitnepal.com/products/d2d980de-71e9-4045-a66a-eb6f47f3550b |
| Gorkha Strong Beer 330ml | Liquors | 200 (MRP 205) | https://www.shopitnepal.com/files/uploads/image/VWBqwN44337386927552.webp | UX/assets/p-liquors-gorkha-strong-beer-330ml.webp | https://www.shopitnepal.com/products/9f4ad977-60c9-4590-b18e-a88f8fd4a236 |
| Haldiram Mexila Nacho Cheese 55g | Packaged Foods | 59 (MRP 60) | https://www.shopitnepal.com/files/uploads/image/twYpqskpk7hehal-mex-.webp | UX/assets/p-packaged-foo-haldiram-mexila-nacho-cheese-55g.webp | https://www.shopitnepal.com/products/89888ebe-fa17-4759-8966-ce27043ee89b |
| Tiffany Digestive Sugar Free 225g | Packaged Foods | 235 (MRP 240) | https://www.shopitnepal.com/files/uploads/image/rqQvV4jpg-b65565f8-a.webp | UX/assets/p-packaged-foo-tiffany-digestive-sugar-free-225g.webp | https://www.shopitnepal.com/products/84d67796-bf55-45bb-a380-32cf589fe18d |
| Coke Zero 250ml | Soft Drinks | 35 (MRP 40) | https://www.shopitnepal.com/files/uploads/image/cApzZcdownload-remov.webp | UX/assets/p-soft-drinks-coke-zero-250ml.webp | https://www.shopitnepal.com/products/f86e27a6-e64c-403b-a319-02dcc46565c0 |
| Fanta 1.5 liter | Soft Drinks | 210 (MRP 220) | https://www.shopitnepal.com/files/uploads/image/7WjxSncaptured-ecran.webp | UX/assets/p-soft-drinks-fanta-1-5-liter.webp | https://www.shopitnepal.com/products/4f032e86-ca31-4bd5-a551-e4ba3382d764 |
| Chicken Steam Momo _(orig: Chicken Steam MoMo)_ | Cloud Kitchen | 270 (MRP 300) | https://www.shopitnepal.com/files/uploads/image/94ad6f3b-72f5-4b93-9b0c-697f6bb638f4-s249nobg.png | UX/assets/p-cloud-kitc-chicken-steam-momo.png | https://www.shopitnepal.com/products/86638d97-376e-476b-807e-10e5eaeaa155 |
| Chicken Fried Momo _(orig: Chicken Fried MoMo)_ | Cloud Kitchen | 270 (MRP 320) | https://www.shopitnepal.com/files/uploads/image/6a24344e-bb76-448a-8b9f-f38f44127c02-s249nobg.png | UX/assets/p-cloud-kitc-chicken-fried-momo.png | https://www.shopitnepal.com/products/e2327d2a-e4c8-42b5-89eb-4ef8a1e973c5 |
| Paneer Momo _(orig: Panner Momo)_ | Cloud Kitchen | 300 (MRP 320) | https://www.shopitnepal.com/files/uploads/image/XQTqKEimages-removeb.webp | UX/assets/p-cloud-kitc-panner-momo.webp | https://www.shopitnepal.com/products/c8d4ddbd-9bc6-4947-a057-d24707baf741 |
| Mutton Momo | Cloud Kitchen | 375 (MRP 450) | https://www.shopitnepal.com/files/uploads/image/2602ded1-da32-4c8e-8fbb-4d49c2eb1604-s249nobg.png | UX/assets/p-cloud-kitc-mutton-momo.png | https://www.shopitnepal.com/products/0053647a-105a-4014-a134-9dca10feadb4 |
| Century Chips Magic Masala | Snacks | 45 (MRP 50) | https://www.shopitnepal.com/files/uploads/image/fGYqLJimages-removeb.webp | UX/assets/p-snacks-century-chips-magic-masala.webp | https://www.shopitnepal.com/products/71d603fd-7bdf-4ba4-b4b6-d5de7d8e7e1e |
| Pringles Cheesy Cheese _(orig: Pringle Cheesy Cheese)_ | Snacks | 145 (MRP 150) | https://www.shopitnepal.com/files/uploads/image/W2vnUZ2738873c-90d6-.webp | UX/assets/p-snacks-pringle-cheesy-cheese.webp | https://www.shopitnepal.com/products/98e91be4-9c41-4889-9a30-b3ae96e69fd3 |
| Nepali Aalu Chips | Snacks | 150 (MRP 170) | https://www.shopitnepal.com/files/uploads/image/v2TK24img-20260603-1.webp | UX/assets/p-snacks-nepali-aalu-chips.webp | https://www.shopitnepal.com/products/6c0659a8-5df8-4e56-ad99-fc7e89c2e46a |
| HiLife Kurum Kurum Chuira 450gm | Snacks | 90 (MRP 95) | https://www.shopitnepal.com/files/uploads/image/Q9iVYr20260205-13362.webp | UX/assets/p-snacks-hilife-kurum-kurum-chuira-450gm.webp | https://www.shopitnepal.com/products/0edb5130-0f8e-4e98-b3f7-b58fd341a99c |
| Wai Wai Hot & Spicy | Snacks | 225 (MRP 250) | https://www.shopitnepal.com/files/uploads/images/products/wai-hot-spi-53aCVhX.webp | UX/assets/p-snacks-wai-wai-hot-and-spicy.webp | https://www.shopitnepal.com/products/1ff853fd-dc5e-4e5a-b9ff-a7655d4aa9ff |
| Rara Noodles | Snacks | 20 | https://www.shopitnepal.com/files/uploads/image/f7cf31f7-b061-409c-947f-b2d30e360143.png | UX/assets/p-snacks-rara-noodles.png | https://www.shopitnepal.com/products/75c409c4-4cac-45fc-902b-3cb3b0a4948a |
| Ponds Pure Detox Face Wash 100gm | Beauty (Personal Care) | 215 (MRP 245) | https://www.shopitnepal.com/files/uploads/images/products/pon-pur-was-100v3byZi.webp | UX/assets/p-beauty-per-ponds-pure-detox-face-wash-100gm.webp | https://www.shopitnepal.com/products/468776c3-3f51-4732-bf91-49ab780dc92b |
| NIVEA Extra Bright Foam 100ml | Beauty (Personal Care) | 440 (MRP 450) | https://www.shopitnepal.com/files/uploads/images/products/niv-ext-bri-100UD9TG4.webp | UX/assets/p-beauty-per-nivea-extra-bright-foam-100ml.webp | https://www.shopitnepal.com/products/39af81cb-1a8d-485b-8de3-bce8d08556e6 |
| VLCC Haldi & Chandan Face Wash 100ml | Beauty (Personal Care) | 225 (MRP 238.4) | https://www.shopitnepal.com/files/uploads/images/products/vlc-hal-cha-fac-100qpVima.webp | UX/assets/p-beauty-per-vlcc-haldi-and-chandan-face-wash-100ml.webp | https://www.shopitnepal.com/products/9bf3a49b-e4e4-4525-a908-694e15b56bfa |
| Mamaearth Ubtan Oil-Free Face Moisturizer | Beauty (Personal Care) | 480 (MRP 510) | https://www.shopitnepal.com/files/uploads/image/ZfpYjrc91ff6d133d919.webp | UX/assets/p-beauty-per-mamaearth-ubtan-oil-free-face-moisturize.webp | https://www.shopitnepal.com/products/2298db84-1652-466c-9181-b7ea4fad0c3d |
| Dove Hair fall Rescue Shampoo 175ml | Beauty (Personal Care) | 225 (MRP 240) | https://www.shopitnepal.com/files/uploads/images/products/dov-hai-sha-175YApwMn.webp | UX/assets/p-beauty-per-dove-hair-fall-rescue-shampoo-175ml.webp | https://www.shopitnepal.com/products/821d488d-a15e-413f-b925-5d9b82a9883d |
| Clinic Plus Egg Shampoo 325ml | Beauty (Personal Care) | 295 (MRP 310) | https://www.shopitnepal.com/files/uploads/images/products/cli-plu-sha-325krMArV.webp | UX/assets/p-beauty-per-clinic-plus-egg-shampoo-325ml.webp | https://www.shopitnepal.com/products/dd40c519-ec29-499c-8ee9-ac80497d9a6a |
