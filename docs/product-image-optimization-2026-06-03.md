# Main Product Photo Optimization — 2026-06-03

Optimized the **main (featured) photo** for 19 Varnem products whose hero image
was still a raw supplier `.jpg` (often a busy infographic, packaging shot, or
multi-image collage). Each was replaced with a clean, photorealistic studio
catalog image. One additional listing — a duplicate — was optimized and then
deleted at the merchant's request (see *Removed* below).

## How it was done

- **Tool:** Higgsfield (`nano_banana_pro` → served as `nano_banana_2`),
  image-to-image, **2K**, **1:1** aspect ratio.
- **Reference:** each product's existing main photo was passed in as the
  reference so the real product (shape, buttons, display, accessories, colors)
  is preserved.
- **Prompt template** (adapted per product):

  > Premium e-commerce product photo in a clean modern catalog style. The
  > \<product\> from the reference image, \<positioning\> on a warm light-gray
  > seamless studio background. Soft diffused lighting, subtle reflection, crisp
  > sharp focus, photorealistic. Preserve the product's real shape, \<key
  > features\>. Correct upright orientation. No added text, no watermark, no
  > logos.

- **Apply method:** the new image was added to each product and moved to
  position 0 (featured) via `productCreateMedia` + `productReorderMedia`.
  **No existing images were deleted** — the original supplier photos remain in
  each product's gallery, so the previous main photo can be restored at any time
  by re-ordering it back to first in Shopify admin.

## Products updated

| # | Product | GID | Previous main (raw) | New main (studio) |
|---|---------|-----|---------------------|-------------------|
| 1 | Digital Multimeter (hFE) | 8763087487030 | 60045ac0…jpg | hf_…17091071.png |
| 2 | 71-in-1 Precision Screwdriver Set | 8763088273462 | 8ba4ad34…jpg | hf_…65f3a164.png |
| 3 | Plastic Welder Kit | 8763088207926 | 6d9a6c98…jpg | hf_…1c1435e6.png (re-gen) |
| 4 | Cordless Electric Screwdriver 4V | 8763088175158 | 086753f4…jpg | hf_…c43ca67f.png |
| 5 | Portable Tire Inflator 12V | 8763087716406 | be5d2ac9…jpg | hf_…bce702d6.png |
| 6 | Epoxy Resin AB Glue | 8763087683638 | cdfb5b86…jpg | hf_…940fbced.png |
| 7 | 6-in-1 Stud Finder Wall Scanner | 8763087650870 | 2f1dc52a…jpg | hf_…11a9f07e.png |
| 8 | Laser Distance Meter | 8763087618102 | b46698bd…jpg | hf_…9c345e1d.png |
| 9 | Rotary Tool Kit | 8763087552566 | 2ae00530…jpg | hf_…34a495f0.png (re-gen) |
| 10 | Digital Caliper | 8763087454262 | 98ad30bd…jpg | hf_…08c51528.png |
| 11 | Ultra-Thin Combination Wrench Set | 8763087355958 | d65b44dc…jpg | hf_…54b18698.png |
| 12 | Mini Cordless Electric Screwdriver | 8763087290422 | b6cd2ea1…jpg | hf_…155cab36.png |
| 13 | Cordless Oscillating Multi-Tool | 8763087257654 | abcd5b04…jpg | hf_…635626e7.png |
| 14 | Waterproof Butyl Seal Tape | 8763087192118 | 86e70acd…jpg | hf_…b5d82177.png |
| 15 | Cordless Angle Grinder 12V | 8763087159350 | 9c581643…jpg | hf_…d984d111.png |
| 16 | Household Hand Tool Kit | 8763087126582 | f9962f72…jpg | hf_…234a672b.png |
| 17 | 170-in-1 Magnetic Screwdriver Set | 8763087061046 | 47878ab2…jpg | hf_…2fe22858.png |
| 18 | Green Laser Level | 8763086995510 | f28ef40e…jpg | hf_…a48a7007.png |
| 19 | Digital Multimeter AN870 (19999 Counts) | 8761819299894 | eb09d0b1…jpg | hf_…d39f48cb.png |

## Removed

- **6In1 Stud Finder Wall Scanner… (8763120189494)** — a duplicate of the active
  "6-in-1 Stud Finder Wall Scanner" listing (#7 above). Per merchant request it
  was **deleted permanently** after first being optimized.

## Notes / known limitations

- **Welder (#3)** and **Rotary Tool (#9)** were regenerated once each: the first
  pass put a misspelled label ("PLASTIC WELEDER") on the welder body, and the
  rotary tool reproduced the reference's bullet-point caption text. Both were
  re-run with an explicit no-lettering / no-captions constraint; the flawed
  images were removed.
- On devices with screens or labels (stud finders, laser meter, caliper, glue,
  multimeters), the model renders realistic on-screen readouts and product
  labels. A few carry a *plausible but fabricated* brand name (e.g.
  "POROMETISTO" on the stud finder); these read as normal retail branding rather
  than defects. Where the brand matched the real product it was preserved
  (e.g. ANENG AN870, INKERSI KE40 laser meter, HILDA laser level, HIPPCRON angle
  grinder, deli screwdriver).
- Tiny micro-text on some dials/labels can be slightly imperfect (typical of AI
  generation) but is not noticeable at thumbnail/hero size.
- Higgsfield credits used: 44 (22 generations × 2 credits).
