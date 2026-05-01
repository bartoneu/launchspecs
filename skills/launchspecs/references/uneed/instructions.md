# Uneed — drafting instructions

Platform-specific guide that the skill follows when generating an Uneed launch kit. The orchestrator (SKILL.md) loads this after the user picks Uneed as a target platform.

## Reference data this guide depends on

Load these alongside this file when drafting:

- [`field-requirements.md`](field-requirements.md): every editor field with its constraint, plus the pre-launch ops checklist.
- [`categories-and-tags.md`](categories-and-tags.md): the 5 categories (single-select) and the 185-tag global pool (multi-select).
- [`image-specs.md`](image-specs.md): logo, images, and launch-video specs with design briefs.
- [`timing-and-scheduling.md`](timing-and-scheduling.md): schedule options, best days, and the rolling-leaderboard mechanic.

## Step UN-1 — Validate against Uneed-official constraints

Before drafting any copy, internalize the constraints from the references above. Treat them as the source of truth. Do not invent constraints not in the references.

## Step UN-2 — Draft text fields

Produce, in English, with strict adherence to character limits (verify with a counter for the Tagline). Apply the brand context detected by the orchestrator's brand-voice step to every field below.

### Name (no hard limit, but keep short and memorable)

The product's name only. Uneed does not enforce a character limit, but the Launch Guide says "short and memorable". Aim for ≤25 characters.

✅ Good: `Linear`, `Notion`, `Figma`.

❌ Bad: `Notion - All-in-one workspace for teams` (descriptor in the name).

### Slug (auto-derived, verify it makes sense)

Uneed auto-derives the slug from the Name (URL-safe, lowercase). Verify it produces a clean URL: `uneed.best/tool/<slug>`. If the auto-derived slug is awkward, suggest an override.

### Tagline (≤80 characters, hard limit, blocks scheduling on overflow)

One sentence that describes the product and earns a click from the listing card.

- Plain language. No marketing-speak ("revolutionary", "game-changing", "unlock the power of").
- Lead with what the product does for the reader, not what it is internally.
- Keep punctuation simple. No emoji unless central to the brand.

Provide **3 tagline options** with a brief rationale for each, then a recommended pick. Verify each is ≤80 chars.

### Rich Description (no character cap; rich-text formatting available)

The body of the product page. Uneed's editor supports bold, italic, strikethrough, inline code, paragraphs, and H1/H2/H3.

Recommended structure:

1. **One-paragraph hook** (~3 sentences). What the product is, who it's for, the core problem it solves.
2. **Key features** as a short list (3-5 items). Bold the feature name, follow with a one-sentence benefit (not a feature description).
3. **What makes it different** (~2 sentences). Specific differentiation against the obvious alternative the reader is comparing you to.
4. **Pricing/offer note** (if applicable). Mention the deal/discount code with the actual offer text.
5. **Closing line**: one short sentence inviting feedback or interaction.

Avoid:

- Feature dumps without context.
- Marketing fluff phrases.
- Headings deeper than H3 (the editor supports it but Uneed pages aren't structured for deep nesting).

### Category (exactly 1 of 5)

Pick the category that matches the **primary user** of the product, not the underlying tech. A no-code site builder used by marketers belongs in Marketing, not Development.

Options: Development, Design, Business, Marketing, Personal Life.

If two categories fit, pick the one where the audience most likely to vote on launch day lives. If still unclear, ask the user.

### Pricing (1 of 3)

Free, Freemium, Paid.

- **Free**: no paid plan exists.
- **Freemium**: usable for free with paid upgrades available.
- **Paid**: requires payment to use (with or without a free trial).

Match the actual pricing model. Mismatches damage trust.

### Tags (3-5 from the 185-tag global pool)

Must come from `categories-and-tags.md`. Do not invent tags.

- Pick 3-5 tightly relevant tags. No upper limit was enforced in the UI, but tag-stuffing hurts perception and discovery.
- One tag should match the technology stack if relevant (Next.js, Python, No-code, etc.).
- One tag should match the use case (CRM, SEO, Newsletter, Project Management, etc.).
- Use specific tags before broad ones. "Cold Emails" beats "Emails"; "Pitch Decks" beats "Templates".
- Avoid mismatches with the chosen Category.

### Deals (optional)

If the product offers a launch discount for the Uneed community, include:

- Deal description (≤30 words): e.g., "30% off the monthly plan for the first 3 months."
- Discount code (uppercase, no spaces): e.g., `UNEED30`.

The deal earns a "Deal" badge on the product card. Skip if there's no real discount; a fake or misleading deal damages trust and can be flagged.

### Socials (optional, all 7 are independent)

Include URLs for any of these the product has: X (Twitter), GitHub, Facebook, Instagram, YouTube, LinkedIn, Bluesky. Leave the rest blank. Don't fabricate handles.

## Step UN-3 — Image generation + specs (always both)

Produce **both** generated images **and** the underlying specs/prompts so the user can hand them to a designer or another tool.

For each image, output:

1. **Generated image file** at the correct dimensions, saved to the platform's output folder.
2. **Specs block** with the exact Uneed constraints (dimensions, format).
3. **Design brief** describing composition.
4. **Prompt** used for generation.

Required and recommended images:

- **1× Logo** (required): square, ≥ 128×128 px (export at 512×512 for safety), PNG with transparent background recommended.
- **1-3× Images** (optional but recommended): same aspect ratio across all of them. The first one functions as a hero card on the listing.
- **Launch video** (optional): if the product benefits from motion, suggest a 60-90s YouTube link. Output the brief, but don't generate the video itself.

See `image-specs.md` for full design-brief templates.

## Step UN-4 — Scheduling guidance

Reference `timing-and-scheduling.md` for the full mechanic. Two rules to apply:

### Rule 1: Day of week

Uneed's Launch Guide recommends Tuesday through Thursday. Avoid weekends and major holidays.

- **Default**: Tuesday or Wednesday.
- **B2B / dev tools / consumer products with weekday usage**: Tue / Wed / Thu.
- **Consumer products with weekend usage habits** (e.g., hobby tools, fitness, journaling): a weekday is still safer; weekends have lower traffic overall.

### Rule 2: Pay vs. join the line

Uneed offers Free (auto-assigned slot) and Skip-the-Line ($29.99, pick the date). Recommend the free path unless the user has:

- A coordinated multi-platform launch (e.g., same day as Product Hunt) where date control matters.
- A press or newsletter date that can't move.
- An auto-assigned slot that lands on a known low-engagement day for their audience.

If none apply, save the $29.99 for paid promotion that actually buys reach (Newsletter Sponsoring or similar).

### Rolling leaderboards: post-launch strategy matters

Unlike Product Hunt's strict 24-hour daily window, Uneed runs Daily / Weekly / Monthly / Yearly leaderboards in parallel. Votes count whenever they come in. Plan for re-engagement:

- 4-7 days after launch: a follow-up newsletter mention to keep Weekly leaderboard activity going.
- 2-3 weeks after launch: a second push for Monthly leaderboard placement.
- Encourage Uneed Pro members in the audience to vote (3× multiplier).

Include this re-engagement plan in the kit, not just the launch-day plan.

### Things this guide does NOT recommend

- ❌ Buying votes or coordinating fake accounts. Uneed has voting moderation; gaming risks the listing.
- ❌ Submitting a product still in private beta. The URL field requires a working public site.
- ❌ Launching on a weekend by default. Lower traffic, weaker leaderboard signal.
- ❌ Stretching multiple categories. Uneed only allows one; the tags shouldn't drag the discovery surface in three directions.
- ❌ Treating Skip-the-Line as automatically better. It buys date control, not vote velocity.

## Step UN-5 — Output the LaunchKit

The orchestrator creates a per-platform folder under the working directory. For Uneed, write the kit to:

```
<product-name>-launch/uneed/
├── kit.md          ← all editor fields, schedule, post-launch plan
├── logo.png        ← square ≥ 128×128 (recommend 512×512)
├── image-1.png     ← hero card (same aspect ratio as image-2, image-3)
├── image-2.png
└── image-3.png     ← if produced; same aspect ratio as the others
```

`kit.md` structure:

```
# [Product Name] — Uneed LaunchKit

## Editor: General tab
[Name, Slug, URL, Category, Pricing, Tags, Tagline, Rich Description, Deals (optional)]

## Editor: Media tab
[Logo (file path + specs), Images 1-3 (file paths + specs), Launch video brief if recommended]

## Editor: Socials tab
[Filled-in social URLs the product actually has]

## Schedule recommendation
[Day of week + free vs. skip-the-line rationale + post-launch re-engagement plan]

## Pre-launch ops checklist
[Pre-launch page setup, "Launching Soon" badge, social posts, announcement email, cross-promo plan]

## Source URLs
[Link back to the references used]
```

Save `kit.md` and any generated image files into the platform folder. When delivering, list the folder path.

## Quality checks before delivering

Before presenting the LaunchKit, verify:

- Brand context check ran. State which sources were applied.
- Name is short and contains only the brand name (no descriptor).
- Tagline is ≤80 chars; 3 options provided, 1 recommended.
- Rich Description has the structured form (hook → features → differentiation → optional offer → closing).
- Category is one of 5; the rationale matches the primary user.
- Pricing matches the actual product pricing model.
- Tags are 3-5, all from `categories-and-tags.md`, none invented.
- Logo brief specifies square ≥ 128×128 and reads well at small sizes.
- Images (if generated) share an aspect ratio.
- Schedule recommendation includes the post-launch re-engagement plan, not just launch day.
- All output is in English.
- Copy reads in the user's brand voice, not generic AI cliché.

## Out of scope

- Submitting the editor or scheduling on the user's behalf. The skill prepares the kit; the user submits.
- Generating Uneed accounts. The user creates the account.
- Recommending paid add-ons (Auto-Submit, Newsletter Sponsoring, Premium Spots) unless the user explicitly asks. Uneed Pro and Skip-the-Line are mentioned where relevant; broader paid promotion is the user's decision, not the skill's recommendation.
