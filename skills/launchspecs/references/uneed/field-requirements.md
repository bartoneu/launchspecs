# Uneed — submission field requirements

Authoritative reference for every field in the Uneed submission flow. Validated against the live submission form and editor on **2026-05-01**.

## Submission flow at a glance

Uneed splits submission into three stages:

1. **Public form** at `/submit-a-tool` collects two fields (Name + URL) and creates the product record.
2. **Editor** at `/edit/waiting-line/{id}` is where the actual launch kit lives. Auto-saves on every change. Robots pre-fill what they can scrape from the URL. Four tabs: General, Media, Socials, Sell.
3. **Schedule launch** picks Free (join the waiting line) or paid Skip-the-Line ($29.99). Existing products can also Relaunch ($15).

The editor sidebar shows a live **completeness checklist**. All 9 required items must be ✅ before scheduling: Name, Slug, URL, Category, Pricing, Tags, Tagline, Rich Description, Logo.

## Step 1 — Public submit form

Endpoint: `https://www.uneed.best/submit-a-tool`

| Field | Required | Notes |
| --- | --- | --- |
| Your product name | ✅ | Used to derive the slug → `uneed.best/tool/<slug>` |
| Your product address | ✅ | Full URL, must include `https://` |

Uneed's robots scrape the page after submit and pre-fill what they can.

## Step 2 — Editor: General tab

| Field | Required | Constraint | Notes |
| --- | --- | --- | --- |
| **Name** | ✅ | No hard `maxLength` enforced in the UI; Launch Guide says "short and memorable" | Pre-filled from Step 1 |
| **Slug** | ✅ | Auto-derived from Name; URL-safe, lowercase | Final URL: `uneed.best/tool/<slug>` |
| **URL** | ✅ | Must be a valid URL | Pre-filled from Step 1 |
| **Category** | ✅ | **Pick exactly 1** of: Development, Design, Business, Marketing, Personal Life | Single-select; see `categories-and-tags.md` |
| **Pricing** | ✅ | One of: Free, Freemium, Paid | Single-select |
| **Tags** | ✅ | At least 1 tag from the global pool of 185 | Multi-select, searchable; see `categories-and-tags.md` |
| **Tagline** | ✅ | **Max 80 characters — hard counter, blocks scheduling on overflow** | Used on the product card in listings |
| **Rich Description** | ✅ | Rich text editor; toolbar supports bold, italic, strikethrough, inline code, paragraphs, H1, H2, H3 | Used on the product page itself; no character cap observed |
| **Deals** | Optional | Two sub-fields: deal description (e.g. "30% off the monthly plan") + discount code (e.g. "UNEED30") | Earns a "Deal" badge on the product card |

## Step 2 — Editor: Media tab

See `image-specs.md` for full visual asset details. Summary:

- **Logo** (required): square, ≥ 128×128 px.
- **Launch Video** (optional): YouTube link, AfterCut link, or direct video URL (`.mp4`, `.webm`).
- **Images** (optional): 1–3 product images, same aspect ratio across all of them.

## Step 2 — Editor: Socials tab (all optional)

Uneed accepts 7 social platforms. Add the ones the product has; leave the rest blank.

| Platform | URL pattern |
| --- | --- |
| X (Twitter) | `https://x.com/<handle>` |
| GitHub | `https://github.com/<handle>` |
| Facebook | `https://facebook.com/<handle>` |
| Instagram | `https://www.instagram.com/<handle>` |
| YouTube | `https://www.youtube.com/@<handle>` |
| LinkedIn | `https://www.linkedin.com/in/<handle>` (or `/company/<handle>`) |
| Bluesky | `https://bsky.app/profile/<handle>` |

## Step 2 — Editor: Sell tab

Out of scope for a launch kit. The Sell tab is a paid listing-for-acquisition feature ($9.99) that surfaces the product to potential buyers. Skill should not generate content for this tab unless the user explicitly asks for it.

## Step 3 — Schedule launch

See `timing-and-scheduling.md` for the full mechanic, best-day guidance, and the rolling-leaderboard rewards. Quick options:

- **Join the line** (free): auto-assigned to the next available launch slot.
- **Skip the line** ($29.99): pick the exact launch date.
- **Relaunch** ($15): re-spotlight an existing product. Included free 1×/month with Uneed Pro.

## Pre-launch ops checklist (Launch Guide guidance, not in the form)

Items to prepare alongside the editor fields:

- [ ] Pre-launch page link (Uneed offers one; collects emails before launch goes live).
- [ ] "Launching Soon on Uneed" badge embedded on the product website.
- [ ] Social posts drafted in advance (X, LinkedIn — see `image-specs.md` for visual asset reuse).
- [ ] Launch announcement email drafted to your existing list.
- [ ] Cross-promo plan: Reddit, IndieHackers, relevant Discord/Slack communities.
- [ ] Logo and image files exported at the right specs (see `image-specs.md`).

## Sources

- [Submit form](https://www.uneed.best/submit-a-tool)
- [Launch Guide](https://www.uneed.best/launch-guide)
- [How it works](https://www.uneed.best/how-it-works)
- [Pricing](https://www.uneed.best/pricing)
