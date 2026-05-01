# Product Hunt — Image specifications and design briefs

All specs validated against PH-official sources ([Help Center](https://help.producthunt.com/en/articles/479557-how-to-post-a-product), [Launch Guide](https://www.producthunt.com/launch/preparing-for-launch)).

## Thumbnail

| Spec | Value | Source |
| --- | --- | --- |
| **Required** | Yes | Step 5 checklist |
| **Dimensions** | **240×240 px (square)** | Both PH-official sources |
| **Max file size** | **3 MB** (PH-official) — form helper UI shows 2 MB; aim for ≤2 MB to stay safe | [Launch Guide](https://www.producthunt.com/launch/preparing-for-launch) |
| **Allowed formats** | JPG, PNG, GIF (per PH docs); WebP also accepted by the form's `accept` attribute (undocumented) | Live form + PH docs |
| **Animated GIFs** | Allowed. Animate on hover only (not autoplay). First frame must be the desired static thumbnail. | [Launch Guide](https://www.producthunt.com/launch/preparing-for-launch) |
| **Editorial caveat** | GIFs with strobing, quick cuts, or unreadable text **may be edited by the PH team**. Use motion sparingly. | [Launch Guide](https://www.producthunt.com/launch/preparing-for-launch) |

### Thumbnail design brief template

> The thumbnail is the single most-seen visual on Product Hunt — it appears on the homepage card, every leaderboard, in the launch archive, and in search results. It must be readable at very small sizes.

Composition rules for a strong PH thumbnail:

1. **Center-weighted, square crop.** No important content within ~10% of the edges (PH may crop slightly in some surfaces).
2. **One focal element.** A logo mark, an iconic UI element, or a single bold visual. No multi-element collages.
3. **High contrast.** It will be shown against PH's white/light backgrounds; dark or saturated thumbnails pop more on the homepage card.
4. **Brand color as the dominant fill.** Helps the launch be recognizable across other surfaces (email, social).
5. **No marketing text** (the tagline lives next to the thumbnail; don't repeat it). Brand wordmark is fine if the brand IS the wordmark.
6. **Accessible at 60×60.** PH downsamples the thumbnail to as small as 60×60 in some surfaces — squint-test it.

### Pre-built design brief — "Brand mark on solid color"
- 240×240 PNG, transparent background OR solid brand color.
- Centered logo or wordmark, ~60% of canvas height.
- 1px-2px contrast margin around the mark.
- Export as PNG (lossless) at ≤500 KB ideally.

### Pre-built design brief — "Iconic UI element"
- 240×240 PNG.
- Single distinctive UI element (a chart, a chat bubble, a unique button) at 70% canvas, centered.
- Solid brand-color background.
- Subtle drop shadow or gradient OK; no skeumorphism.

### Pre-built design brief — "Animated GIF (use carefully)"
- 240×240 GIF, ≤3 MB, ≤30 frames.
- The static first frame must work as a standalone thumbnail (it's what shows on hover-less surfaces).
- Single-loop ideally; subtle motion (pulse, slide, fade) — not video-style.
- ❌ No strobing, no rapid cuts, no scrolling text.

## Gallery images

| Spec | Value | Source |
| --- | --- | --- |
| **Minimum** | **2 images required** for the gallery to be viewable | [Launch Guide](https://www.producthunt.com/launch/preparing-for-launch), [Help Center](https://help.producthunt.com/en/articles/479557-how-to-post-a-product) |
| **Form recommendation** | "We recommend at least 3 or more images" (form helper) | Live form |
| **Dimensions** | **1270×760 px (landscape, ~5:3 aspect ratio)** | Both PH-official sources |
| **Max file size** | Not explicitly stated; same input family as thumbnail → assume **≤3 MB per image** | Inferred |
| **Allowed formats** | JPG, PNG, GIF (animated GIFs allowed); WebP accepted by form | Live form + PH docs |
| **Reordering** | Drag-and-drop after upload (or keyboard: space to grab, arrows to move, escape to cancel) | Live form |
| **First image role** | **Becomes the OG/social-share preview** when the launch URL is shared on X, LinkedIn, Slack, etc. | [Launch Guide](https://www.producthunt.com/launch/preparing-for-launch) |

### Gallery image #1 — design brief (the social/OG card)

**Critical:** This image is what people see when the launch URL is shared anywhere off-Product-Hunt. Design it as a hero card, not a screenshot.

Composition:

1. **1270×760 PNG**, ≤3 MB.
2. **Brand color as background** OR a high-quality product backdrop (UI wireframe softly faded).
3. **Logo + product wordmark** (top-left or centered, ~10-15% of canvas).
4. **Tagline as headline** (large type, ≤8 words, easy to read on a small mobile preview).
5. **One supporting visual** — a screenshot of the most distinctive UI element, OR an icon system, OR a hero illustration.
6. **No call-to-action button.** OG cards are previews, not landing pages.
7. **Brand-consistent typography** — match the product's website if possible.

### Gallery images #2-N — design brief (product walkthrough)

These are the in-PH gallery the maker scrolls through. Use them to tell the story of the product:

| Image # | Suggested content |
| --- | --- |
| 2 | The "before" state — the problem the product solves, illustrated with a UI screenshot of what the user does today (on a competitor or manually). |
| 3 | The "after" state — the product's main interface solving that problem. Annotate the key UI element with a callout. |
| 4 | Secondary feature — second most important capability, screenshot + 1-2 sentence callout. |
| 5 | A user testimonial or social-proof element if available — quote + name + headshot, designed as a clean card. |
| 6 | A pricing or "how to get started" panel — only if the product has a self-serve flow; otherwise skip. |

Composition rules for gallery images #2+:
- 1270×760 PNG.
- Generous whitespace — at small sizes, PH downsamples; busy screenshots become illegible.
- Each image conveys ONE idea — don't cram multiple features in one image.
- Optional but effective: a 4-8 word headline at the top of each image describing what's shown.

## Video (optional, but recommended)

| Spec | Value | Source |
| --- | --- | --- |
| **Source** | **YouTube only** (PH-official). Form helper mentions Loom, but PH docs say only YouTube links work. | [Launch Guide](https://www.producthunt.com/launch/preparing-for-launch), [Help Center](https://help.producthunt.com/en/articles/479557-how-to-post-a-product) |
| **URL format** | **Full URL** (`youtube.com/watch?v=...`) — shortened `youtu.be` links will not load | [Help Center](https://help.producthunt.com/en/articles/479557-how-to-post-a-product) |
| **Privacy** | Must NOT be set to private | [Help Center](https://help.producthunt.com/en/articles/479557-how-to-post-a-product) |
| **Recommended length** | ≤90 seconds for a product demo; ≤2 min for a maker story | Industry convention |
| **PH-cited stat** | 53% of Product of the Day launches since 2021 included a video | [Launch Guide](https://www.producthunt.com/launch/preparing-for-launch) |

Workflow if you want to use Loom for ease: record in Loom → download → upload to YouTube (set to public/unlisted, NOT private) → submit the YouTube URL to PH.

## Interactive demo (optional)

Free for PH launches via these tools (output a link, paste into the demo URL field):

| Tool | URL |
| --- | --- |
| Arcade | https://www.arcade.software/?ref=producthunt |
| Storylane | https://www.storylane.io/?ref=producthunt |
| Hexus | https://www.hexus.ai/product-hunt/?ref=producthunt |
| Supademo | https://supademo.com/?ref=producthunt |
| Layerpath | https://www.layerpath.com/?ref=producthunt |
| ScreenSpace | https://screenspace.io/?ref=ph |
| Guideflow | https://www.guideflow.com/?ref=producthunt |

Per PH: *"The most successful launches tell a compelling story of the product, including showing what the user interface looks and feels like."* Interactive demos beat static gallery images for complex products.

## Asset checklist for a launchkit

Before submission, the maker should have on hand:

- [ ] Thumbnail at 240×240 (PNG, ≤2 MB ideally, ≤3 MB hard limit) — §thumbnail
- [ ] Gallery image #1 (social/OG preview card) at 1270×760 — §gallery
- [ ] Gallery images #2-3 (or more) at 1270×760 — §gallery
- [ ] Optional: animated GIF version of any of the above
- [ ] Optional: YouTube video link, public, full URL — §video
- [ ] Optional: interactive demo link from one of the listed tools — §demo
