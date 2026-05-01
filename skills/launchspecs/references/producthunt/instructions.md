# Product Hunt — drafting instructions

Platform-specific guide that the skill follows when generating a Product Hunt launch kit. The orchestrator (SKILL.md) loads this after the user picks Product Hunt as a target platform.

## Reference data this guide depends on

Load these alongside this file when drafting:

- [`field-requirements.md`](field-requirements.md): every form field with its hard constraint.
- [`launch-tags.md`](launch-tags.md): the enumerated 419-tag list.
- [`image-specs.md`](image-specs.md): thumbnail and gallery specs with design briefs.
- [`first-comment.md`](first-comment.md): first-comment rules and the AI-ban scaffold template.
- [`shoutouts.md`](shoutouts.md): Shoutouts mechanics and selection strategy.
- [`timing-and-scheduling.md`](timing-and-scheduling.md): launch-time mechanic, day-of-week tradeoffs, 2026 algorithm shift.

## Step PH-1 — Validate against PH-official constraints

Before drafting any copy, internalize the constraints from the references above. Treat them as the source of truth. Do not invent constraints not in the references.

## Step PH-2 — Draft text fields

Produce, in English, with strict adherence to character limits (verify with a counter). Apply the brand context detected by the orchestrator's brand-voice step to every field below — the output should sound like the user's brand, not a generic AI draft.

### Name (≤40 characters)

The product's name only. No tagline-style descriptors, no emojis (unless a literal part of the brand name).

✅ Good: `Linear`, `Notion`, `Figma` — just the brand name.

❌ Bad: `Linear · Issue tracking for modern teams`, `Notion - All-in-one workspace`.

### Tagline (≤60 characters)

One catchy sentence. The single biggest driver of clicks from the homepage card.

- No gimmicks, no over-the-top language.
- Plain language wins.

✅ Good: "Send your friends a voicemail meow from a real cat." (PH's own example)

❌ Bad: "The most ameozing app in the app store" (gimmicky, no info).

Provide **3 tagline options** with a brief rationale for each, then a recommended pick.

### Description (≤500 characters)

Articulates the product's value proposition AND what's different vs. existing alternatives.

- Plain prose, can use a short list, no marketing jargon.
- Cite specifically what's new/different. The form's own helper says "What's new or different about your launch compared to existing products?"

### Launch tags (1–3 from the enumerated list)

Must come from `launch-tags.md`. Do not invent tags.

- Pick 2-3 tags that *most strongly* relate to the product. Don't stretch.
- If the product has a primary use case (e.g., AI coding) and a secondary surface (e.g., team collaboration), include both.
- Sub-tags are valid selections (e.g., `Hiring` lives under `Business`; both are pickable independently).

### Shoutouts (3 product candidates + a "why" note for each)

Tools/services that genuinely helped build the product.

- Each note should be 1-2 sentences explaining the specific contribution.
- These notes become permanent founder-reviews on the recipient's page. Write them like useful reviews, not generic shoutouts.
- See `shoutouts.md` for the strategy and examples.

## Step PH-3 — First comment scaffold

**CRITICAL:** Product Hunt explicitly bans LLM-generated comments ([Commenting Guidelines](https://help.producthunt.com/en/articles/10030102-commenting-guidelines)):

> *"Product Hunt is about person-to-person interactions. Our community wants to talk to and hear from real people. **No LLMs or Chrome extensions please!**"*

The skill must NOT produce a turnkey first comment that the maker pastes verbatim. Instead, produce a **scaffold**: a structured outline with placeholder phrasing and explicit annotations marking what the maker needs to personalize.

Scaffold structure:

1. **Opening hook** (1-2 sentences): maker's personal connection to the problem. Mark as `[REWRITE IN YOUR OWN VOICE — share a real anecdote]`.
2. **What it is**: 1 sentence on the product.
3. **Who it's for**: explicit target user.
4. **Key features**: short bullet list (3-5 items max), bold the feature name.
5. **What makes it different**: 1-2 sentences.
6. **Pricing/offer note** (if applicable): link to promo code.
7. **Ask for feedback** (NOT upvotes): specific question(s) the maker wants the community to answer.
8. **Closing**: thank-you, optional emoji.

After producing the scaffold, output a clear notice:

> ⚠️ **PH bans AI-generated comments.** This is a scaffold. Before posting, rewrite the marked sections in your own voice with real anecdotes and specific phrasing only you would use. Comments that read as LLM-generated may be hidden by PH moderation.

## Step PH-4 — Image generation + specs (always both)

Produce **both** generated images **and** the underlying specs/prompts so the user can hand them to a designer or another tool if the generated output isn't right.

For each image, output:

1. **Generated image file** at the correct dimensions, saved to the platform's output folder.
2. **Specs block** with the exact PH constraints (dimensions, max file size, format).
3. **Design brief** describing composition, color palette, type, message hierarchy. Written so a human designer or any image-gen tool could produce a comparable asset.
4. **Prompt** used for generation, so the user can iterate.

Required images:

- **1× Thumbnail** at 240×240 (square, ≤3 MB, JPG/PNG/GIF/WebP). The single most-seen visual.
- **2-3× Gallery images** at 1270×760 (landscape, ≤3 MB each). The first one becomes the OG/social-share preview, so design it as a hero card (logo + tagline + visual hook), not a screenshot dump.

See `image-specs.md` for full constraint details and design-brief templates.

If image generation tools aren't available in the current environment, output specs + briefs + prompts only and tell the user explicitly: "I produced specs and prompts but couldn't generate the image files in this environment. Paste the prompts into [tool] or hand the briefs to your designer."

## Step PH-5 — Scheduling guidance

Reference `timing-and-scheduling.md` for the full mechanic. Two rules to apply:

### Rule 1: Time of day = always 12:01 AM PST

PH's daily window opens at 12:01 AM PST. The first 4 hours are a hidden-vote phase where products are shown in randomized order to give everyone equal exposure. At 4:01 AM PST the leaderboard re-sorts by accumulated votes. Launching later than 12:01 AM PST means missing part of the equal-exposure window AND starting the visible leaderboard already behind. There is no scheduling tactic that makes a non-12:01-PST launch better.

### Rule 2: Day of week = pick based on product type

- **B2B / enterprise / dev tools**: recommend **Tuesday or Wednesday** at 12:01 AM PST.
- **Consumer / solo / side project**: recommend **a weekend day** at 12:01 AM PST (less competition; PH-cited +15% Visit clicks vs. weekdays).
- **Default if unclear**: Tuesday at 12:01 AM PST.
- **Avoid Mondays and Fridays** by default (slow start / early-checkout days).

### When the user has a hard external dependency

If the user names a hard external constraint (immovable press embargo, regulatory date), recommend 12:01 AM PST anyway and tell them:

> "Launching at the embargo time means you skip part or all of the 4-hour hidden-vote window, and you'll start the visible leaderboard already behind. This is a real cost in launch position. If the embargo can be moved to align with 12:01 AM PST, do that instead."

If the dependency truly cannot move, schedule to it but flag the cost explicitly. Do not frame this as an alternative optimization.

### Schedule horizon

Up to 1 month in advance. Booking the slot early just reserves the date. There is no longer a "tease the launch" feature, so don't promise pre-launch follower-collection.

### 2026 algorithm shift to flag in the kit

PH's algorithm now weighs **engagement signals** (comments, maker replies, time-on-page, verified-user activity) more than raw upvote counts. Include in the kit a "launch-day engagement plan" item: which makers are online during which hours of launch day to reply to comments, ask follow-up questions, and keep the conversation alive. Block the first 4 hours minimum on the maker's calendar.

### Things this guide does NOT recommend

- ❌ Launching later in PT day to align with non-US audience timezones.
- ❌ "Aligning to press embargo" framed as a positive tactic.
- ❌ Friday launches by default.
- ❌ Any deviation from 12:01 AM PT that isn't forced by an external constraint the user can't move.
- ❌ Promising "tease + collect followers ahead of launch" — that feature no longer exists.

## Step PH-6 — Output the LaunchKit

The orchestrator creates a per-platform folder under the working directory. For Product Hunt, write the kit to:

```
<product-name>-launch/producthunt/
├── kit.md              ← all submission fields, scaffold, schedule
├── thumbnail.png       ← 240×240
├── gallery-1.png       ← 1270×760, hero card
├── gallery-2.png       ← 1270×760
└── gallery-3.png       ← 1270×760 (if produced)
```

`kit.md` structure:

```
# [Product Name] — Product Hunt LaunchKit

## Submission fields
[Name, Tagline, Description, Launch tags, Pricing, Promo, Open source flag, X handle, URL]

## Visual assets
[Thumbnail, Gallery (with file paths to generated images, plus specs and briefs)]

## First comment scaffold
[The scaffold + the AI-warning notice]

## Shoutouts
[3 product candidates with "why" notes]

## Schedule recommendation
[Specific date/time + rationale]

## Pre-launch ops checklist
[All ops items the maker needs to do before submitting]

## Source URLs
[Link back to the references used]
```

Save `kit.md` and any generated image files into the platform folder. When delivering, list the folder path so the user can open it directly.

## Quality checks before delivering

Before presenting the LaunchKit, verify:

- Brand context check ran. State which sources were applied (or that none were found and which fallback was used).
- Name is ≤40 chars and contains only the brand name (no descriptor).
- Tagline is ≤60 chars; 3 options provided, 1 recommended.
- Description is ≤500 chars and articulates differentiation.
- Launch tags are 1-3, all from `launch-tags.md`, none invented.
- First comment is a SCAFFOLD with the AI-ban warning. Not a turnkey comment.
- Shoutout notes are specific (1-2 sentences each on the actual contribution).
- Image briefs include exact dimensions and the OG-card design pattern for the first gallery image.
- All output is in English.
- No links to bit.ly or UTM-tracking URLs anywhere in the submission fields.
- Copy reads in the user's brand voice, not generic AI cliché ("revolutionary", "game-changing", "unlock the power of", etc.).

## Out of scope

- Launching/submitting the form on the user's behalf. The skill prepares the kit; the user submits.
- Generating maker accounts on Product Hunt. The maker must create accounts themselves and ensure co-makers also have PH accounts before launch day.
- Gaming upvotes or any growth-hacky tactics that violate PH's [community guidelines](https://help.producthunt.com/en/articles/3615694-community-guidelines).
