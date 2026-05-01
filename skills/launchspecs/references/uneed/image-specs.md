# Uneed — image and media specifications

Validated against the live editor's Media tab on 2026-05-01.

## Logo (required)

| Spec | Value | Notes |
| --- | --- | --- |
| Required | Yes | Part of the 9-item completeness checklist |
| Shape | **Square** | UI explicitly recommends a square format |
| Minimum size | **128×128 px** | Under-spec uploads not formally rejected, but the guide says ≥128×128 |
| Format | PNG, SVG, JPG implied | Not surfaced in UI; PNG with transparent background is the safe default |
| File size | Not documented | Keep ≤ 1 MB to stay safe |

### Logo design brief

The logo is the most-seen visual on Uneed: it appears on every leaderboard card, on the product page header, in the newsletter, and as the favicon on the product's `uneed.best/tool/<slug>` page.

Composition rules:

1. **Center-weighted, square crop.** No important content within ~10% of the edges.
2. **One focal element.** A logo mark or wordmark, not a collage.
3. **Brand color as dominant fill** for visual recognition across surfaces.
4. **Readable at 32×32.** Uneed downsamples for small surfaces (newsletter thumbnails, sidebar widgets); squint-test at very small sizes.
5. **Transparent background** if PNG, so the logo works on Uneed's light and dark UI.
6. **No marketing text in the logo.** The tagline lives next to it on every card.

## Images (optional, recommended)

| Spec | Value | Notes |
| --- | --- | --- |
| Count | 1–3 images | Hard limit |
| Aspect ratio | **Same across all uploaded images** | Uneed's guide explicitly recommends consistency |
| Format | Implied PNG/JPG | Not surfaced in UI |
| File size | Not documented | Keep each ≤ 2 MB |

### Images design brief

Use these to tell the product story on the listing page. The first image is the most-seen and should function as a hero card, similar to a social/OG preview.

Suggested image sequence:

| Image # | Suggested content |
| --- | --- |
| 1 | Hero card. Brand color background, logo + product wordmark, tagline as headline (≤ 8 words), one supporting visual (most distinctive UI element or hero illustration). Designed to read well as a thumbnail. |
| 2 | Primary feature shot. UI screenshot of the most distinctive interaction or output, with one bold annotation explaining what's shown. |
| 3 | Secondary feature shot OR social-proof element (testimonial, user count, customer logo wall). Same aspect ratio as the first two. |

Composition rules across all images:

- Generous whitespace. Listing surfaces downsample, so busy screenshots become illegible.
- One idea per image. Don't cram features.
- A short headline (≤ 8 words) on each image is optional but effective; keep it readable when the image is sized down.
- Same aspect ratio across all uploaded images, per Uneed's guide.

## Launch Video (optional)

| Spec | Value | Notes |
| --- | --- | --- |
| Source | YouTube link, AfterCut link, or direct video URL (`.mp4`, `.webm`) | Editor accepts a single URL |
| Hosting | YouTube is the safest choice for reach and reliability | AfterCut is an Uneed partner; first export is free |
| Privacy | YouTube link must NOT be private | Standard for embedded video |
| Length | Not enforced | Keep product demos ≤ 90 seconds; maker-story videos ≤ 2 minutes |

A launch video is optional but recommended for products where the value is hard to convey in a static image (interactive tools, complex UIs, anything with motion).

## Asset checklist before scheduling

Before clicking "Schedule launch", confirm:

- [ ] Logo at ≥ 128×128 square (PNG with transparent background recommended).
- [ ] 1–3 product images at the same aspect ratio across all of them.
- [ ] Optional: launch video URL (YouTube public/unlisted, AfterCut, or direct `.mp4`/`.webm`).
- [ ] First image designed as a hero card so it works as a thumbnail on listings and in the newsletter.
- [ ] Embed asset for the "Launching Soon on Uneed" badge on the product website (optional but Launch-Guide-recommended).

## Sources

- [Live editor Media tab](https://www.uneed.best/edit/waiting-line/) (requires authenticated session)
- [Launch Guide](https://www.uneed.best/launch-guide)
