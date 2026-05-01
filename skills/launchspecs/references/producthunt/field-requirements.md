# Product Hunt submission — field requirements

Authoritative reference for every field in the PH submission form. All constraints validated against the live form (2026-04-29) and PH-official documentation.

## Required fields (form blocks submission without these)

| # | Field | Type | Hard constraint | Source |
| --- | --- | --- | --- | --- |
| 1 | **Name** | text, ≤40 chars | Product name only — no description, no emojis (unless literal part of name) | [Launch Guide](https://www.producthunt.com/launch/preparing-for-launch) |
| 2 | **Tagline** | text, ≤60 chars | Plain language, no gimmicks, no over-the-top language | [Launch Guide](https://www.producthunt.com/launch/preparing-for-launch) |
| 3 | **Primary URL** | URL | Direct link to product page. **No shortened links** (bit.ly etc.). **No tracking links** (UTMs etc.). | [Launch Guide](https://www.producthunt.com/launch/preparing-for-launch) |
| 4 | **Description** | textarea, ≤500 chars | Articulate value prop AND differentiation vs. existing products | Form helper + [Launch Guide](https://www.producthunt.com/launch/preparing-for-launch) |
| 5 | **Launch tags** | multi-select, 1–3 | Must be from the enumerated list (see launch-tags.md). Strongly relevant only — don't stretch. | [Launch Guide](https://www.producthunt.com/launch/preparing-for-launch) |
| 6 | **Thumbnail** | image upload | Square, recommended 240×240 px, ≤3 MB | [Help Center](https://help.producthunt.com/en/articles/479557-how-to-post-a-product), [Launch Guide](https://www.producthunt.com/launch/preparing-for-launch) |
| 7 | **Gallery** | multi-image upload | **Minimum 2 images.** Recommended 1270×760 px each. First image becomes the OG/social preview. | [Help Center](https://help.producthunt.com/en/articles/479557-how-to-post-a-product), [Launch Guide](https://www.producthunt.com/launch/preparing-for-launch) |

## Strongly Recommended fields (form's own checklist marks these "Strongly Recommended")

| # | Field | Type | Why it matters | Source |
| --- | --- | --- | --- | --- |
| 8 | **First comment** | textarea | 70% of products that achieved Product of Day/Week/Month had a first comment by the maker | [Launch Guide](https://www.producthunt.com/launch/preparing-for-launch) |
| 9 | **Video** | URL (YouTube only) | 53% of Product of the Day launches included a video | [Launch Guide](https://www.producthunt.com/launch/preparing-for-launch) |
| 10 | **Additional Makers** | multi-input (PH usernames or emails) | Maker followers receive email if launch hits homepage; Hunter followers do not | [Help Center](https://help.producthunt.com/en/articles/479557-how-to-post-a-product) |
| 11 | **Shoutouts** | up to 3 PH products + note each | Becomes a permanent founder-review on each recipient's page → durable distribution | [Introducing Shoutouts](https://www.producthunt.com/stories/introducing-shoutouts) |

## Optional fields

| Field | Type | Notes |
| --- | --- | --- |
| **Additional URLs** | multi (App Store, Google Play, Steam, Amazon, etc.) | "+ Add more links" in the form |
| **X (Twitter) account** | text (handle only, prefix is `x.com/`) | Use the **product's** brand handle, not a personal one |
| **Open source flag** | checkbox | Adds an open-source signal to the launch page |
| **Pricing** | radio: Free / Paid / Paid (with free trial or plan) | "Optional, but the community really appreciates knowing." |
| **Promo code** | 3 text fields (offer, code, expiration) | All three required if any one is filled |
| **Interactive demo URL** | URL | Free for PH launches: Arcade, Storylane, Hexus, Supademo, Layerpath, ScreenSpace, Guideflow |

## Form structure (5 steps)

1. **Main info** — Name, Tagline, URL, Open source flag, X handle, Description, Launch tags, First comment
2. **Images and media** — Thumbnail, Gallery, Video, Interactive demo
3. **Makers** — Hunter/Maker self-declaration, additional Makers (Shoutouts likely lives here as a sub-block per the [Shoutouts announcement](https://www.producthunt.com/stories/introducing-shoutouts))
4. **Extras** — Pricing, Promo code
5. **Launch checklist** — final review with required + recommended split, then Schedule or Create draft

## Hunter vs. Maker (Step 3.1)

Two distinct roles on every launch:

- **Hunter** = the person submitting the post.
- **Maker** = the people who built the product.
- One person can be both. PH explicitly recommends posting your own product (don't pay a hunter — see [Before launch](https://www.producthunt.com/launch/before-launch#hunters:-do-you-need-one?)).
- **Notification asymmetry:** Hunter's followers do NOT receive email notifications. Maker's followers DO receive an email IF the launch ends up on the homepage. Implication: being listed as a Maker is more distribution-valuable than only being a Hunter.
- Personal account required. Company accounts cannot post.

## Image MIME types accepted by the form

Per the live form's `accept` attribute: `image/gif`, `image/jpeg`, `image/png`, `image/webp`. WebP is technically accepted by the form but not mentioned in any PH-official doc. JPG/PNG/GIF are the safe set.

## Discrepancies between live form and PH-official docs

When in doubt, the live form is authoritative for what works; the help docs are authoritative for editorial best practices.

| # | Field | Live form | PH-official docs | Take |
| --- | --- | --- | --- | --- |
| 1 | Description max | 500 chars | Help Center says 260; Launch Guide says 500 | Use **500** (form + Launch Guide agree; Help Center is older) |
| 2 | Thumbnail max size | Form helper: 2 MB | Both PH docs: under 3 MB | **3 MB** is the documented hard limit; design for ≤2 MB to stay within the form's UI guidance |
| 3 | Video sources | Form: "YouTube or Loom" | Both docs: **only YouTube** | Build with Loom for speed → upload final to YouTube → submit YouTube URL |
| 4 | Image format helper | Form helper: JPG/PNG/GIF (no WebP) | Same | Form's `accept` also allows **WebP** (undocumented) — safer to ship JPG/PNG/GIF |
| 5 | Demo tools | Form lists 7 (incl. Guideflow) | Launch Guide lists 6 (no Guideflow) | All accepted; Guideflow is a more recent partner |

## Pre-launch ops checklist (PH-official guidance, not in the form)

- All co-makers have a PH account created (well before launch day, not day-of).
- Schedule slot picked (12:01 AM PST optimal; up to 1 month ahead).
- Day-of-week chosen (weekdays = bigger competition; weekends = +15% Visit clicks for solo/personal/side-project launches).
- Press / news embargo aligned (if any) to the same scheduled minute.
- Hunter/Maker assignment decided.
- Personal account used (company accounts cannot post).
- Maker's PH profile is complete (full name, real photo, informative bio) — incomplete profiles risk having comments auto-hidden by moderation.
