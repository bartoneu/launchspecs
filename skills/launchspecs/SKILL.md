---
name: launchspecs
description: Produce complete, submission-ready launch kits for indie launch platforms (Product Hunt and Uneed, with Peerlist/BetaList coming) from a product brief. The skill identifies which platform(s) the user is targeting, loads only the platform-specific instructions and reference data needed, and outputs platform-tailored kits — name, tagline, description, tags or categories, image specs, scheduling guidance, and any platform-specific artifacts (PH first-comment scaffold, Uneed deals, etc.) — into a per-platform folder under the working directory. Use when the user asks to "prep a launch", "create a launch kit", "draft Product Hunt copy", "prep a Uneed launch", "launch this on multiple platforms", or anything about preparing a submission to an indie launch platform. The skill enforces every platform-official constraint and produces output in English.
argument-hint: "[product name or brief, optionally with target platforms]"
version: 1.0.0
last-verified: 2026-05-01
supported-platforms:
  - producthunt
  - uneed
---

# launchspecs

> ⚠️ **Unofficial, community-maintained skill.** Not affiliated with, endorsed by, or sponsored by Product Hunt, Uneed, or any other launch platform. All platform names and marks belong to their respective owners.

Produce complete, submission-ready launch kits for indie launch platforms from a product brief. The skill identifies the target platform(s) from the user's request (or asks if not specified), loads only the platform-specific instructions and references it needs, and writes a per-platform output folder containing a `kit.md` with all submission fields plus any generated visual assets.

When the user is launching to multiple platforms at once, the skill cross-aligns the copy so the same product story holds across all submissions while respecting each platform's specific constraints.

Outputs are always in **English** regardless of input language. Indie launch platforms are US/global communities and submissions are read by English-speaking audiences.

## Currently supported platforms

- **Product Hunt** (`references/producthunt/`): full coverage of form fields, 419 launch tags, image specs, first-comment scaffold with the PH AI-comment ban handled correctly, Shoutouts, scheduling with the 4-hour hidden-vote window and 2026 algorithm changes.
- **Uneed** (`references/uneed/`): full coverage of editor fields, 5 categories, 185-tag global pool, image specs, optional deals, schedule options (Free / Skip-the-Line / Relaunch), rolling-leaderboard strategy.

Coming next: Peerlist, BetaList. PRs welcome (see the repo README).

## When to invoke

User asks to prepare anything for a launch on a supported platform:

- "Prep a Product Hunt launch for [product]" / "Create a PH launchkit"
- "Prep a Uneed launch" / "Create a Uneed launchkit"
- "Launch this on Product Hunt and Uneed" (multi-platform)
- "Draft tagline / description / first comment for [platform]"
- "What tags should I pick for [platform]?"
- "Make a thumbnail / logo for [platform]"
- "How should I schedule my [platform] launch?"

Do NOT invoke for: discovering brand voice, generating brand guidelines, or non-launch content (use the brand-voice or marketing skills for those).

## Process

The skill runs as an orchestrator. It identifies the target platform(s), gathers product context, detects brand voice, then hands drafting off to the platform-specific instructions file. The orchestrator only contains the cross-platform steps below.

### Step −1 — Identify the target platform(s) (always ask)

Even if the user named a platform in the request, **always run an AskUserQuestion** to confirm the target list. The user may want to add platforms they didn't think to mention, or change the scope after seeing what's supported.

**How to ask:**

Use AskUserQuestion with the question:

> "Which platform(s) are you launching on?"

Option list (multi-select):

- **Product Hunt**
- **Uneed**
- (Add other supported platforms as they land in `supported-platforms` in this skill's frontmatter.)

If the user named a platform in their original request, **pre-select it** in the AskUserQuestion options so confirmation is one click. The user can still add or remove platforms.

**If the user names an unsupported platform** (e.g., Peerlist or BetaList before they're added), explain explicitly: "I don't have reference data for [platform] yet. I can produce kits for [supported platforms] now. Want to proceed without [platform], or wait until it lands?"

**State the chosen platform(s) at the start of your output.** Examples:

> *Targeting: Product Hunt. Loading `references/producthunt/`.*

> *Targeting: Product Hunt + Uneed. Producing one kit per platform with cross-aligned copy.*

**Reference loading:** load `references/<platform>/instructions.md` and the platform's other reference files **only for chosen platforms**. Do not load references for platforms not in scope; they would burn context window for no value.

### Step 0 — Gather product context (context-first, questions-last)

The whole value of this skill is leveraging context the user has already collected (landing pages, Notion docs, briefs, internal positioning files) instead of asking them to retype everything. Always try to pull context first; only fall back to manual questions for what you couldn't find.

#### Step 0.1 — Ask where to pull context from

Via AskUserQuestion (or in chat if more natural):

> "Where can I pull product context from? Pick all that apply."

Offer these options (multi-select):

- **Files attached to this conversation** (PDFs, Markdown, Notion exports, briefs).
- **Files in my workspace folder** (the user's mounted folder; list relevant-looking files: `brand-*.md`, `messaging*.md`, `*-brief*`, `positioning*.md`, etc.).
- **A Notion page or workspace** (paste URL; use the Notion MCP tool if available).
- **The product's live website** (paste URL; use `web_fetch` to read landing page, /about, /pricing).
- **An existing launch on one of the target platforms** (paste the URL; use `web_fetch` to grab the existing kit as a reference).
- **A short description in chat** (only if the above don't apply).
- **Skip — no context yet**, I'll provide everything by hand.

#### Step 0.2 — Read everything the user pointed to

- **Uploaded files / workspace files**: use `Read` for each. Prioritize landing page copy, marketing positioning docs, brand voice guides.
- **Notion URLs**: use the Notion MCP tools (`notion-fetch`, `notion-search`) if connected. If not connected, surface the missing connector to the user.
- **Web URLs**: use `web_fetch` for the homepage, `/pricing`, `/about`, plus 1-2 deep pages if linked from the homepage. Don't crawl indiscriminately.
- **Previous launch URL**: use `web_fetch` to grab the existing tagline, description, gallery, first comment as a starting reference.

Build an internal context summary: product name, what it does, who it's for, pricing, key features, differentiators, brand voice signals, visual assets available.

#### Step 0.3 — Identify gaps and ONLY THEN ask

Compare the assembled context against what the kit actually needs. For anything still missing, ask the user, but **batch the gaps into a single AskUserQuestion call**. Don't drip-ask.

If the user picked "Skip — no context yet", fall through to a full input collection.

#### Step 0.4 — Required vs. derived fields (cross-platform)

| Kit needs | Usually derivable from… | Ask user only if not derivable |
| --- | --- | --- |
| Product name | Landing page header, Notion page title | If ambiguous (multiple working names) |
| One-sentence pitch | H1 / hero subhead on landing page | If landing page is wordy or vague |
| What's new / differentiator | "Why us" section, comparison docs, blog announcements | Almost always partially. Ask for the *one* thing the user wants the launch to lead with |
| Target audience | "For [X]" hero, persona docs, ICP doc | If audience isn't named explicitly anywhere |
| Pricing model | `/pricing` page, sales deck | If pre-pricing or stealth |
| Maker story | About page, founder blog post, "Why we built this" | If no public-facing version exists, ask for 2-3 sentences |
| Key features | `/features`, product tour, marketing site | Almost always derivable; verify priority order with user |
| Visual brand assets | Logo file, brand color in CSS, screenshots in marketing site | If no docs and no marketing site, request files |
| Launch date target | Roadmap, calendar | Always ask. Not in product docs |

Platform-specific fields (PH Shoutouts candidates, Uneed deal/discount code, etc.) are gathered by the platform's `instructions.md` once the orchestrator hands off.

#### Step 0.5 — State what was sourced

When delivering the kit(s), include a "Context sourced from" line at the top, e.g.:

> *Context sourced: landing page copy from acmeproduct.com + 2 Notion pages + 1 brief uploaded to chat. Asked user for: launch date, 3 Shoutouts candidates.*

This makes it auditable.

### Step 1 — Detect and apply the user's brand context

Before drafting copy, check whether the user has any pre-existing copywriting / brand-voice setup and apply it. The output should sound like the user's brand, not a generic AI draft.

**Check three places, in this order:**

**(a) Installed Cowork skills relevant to copy quality.** Inspect the `<available_skills>` list for any of these and apply them when drafting:

- `copywriting`: universal writing-quality skill. **If installed, treat it as the baseline standard for all generated copy** (Name, Tagline, Description, scaffolds). It eliminates AI writing patterns and applies persuasion principles. Always prefer applying it over not.
- `brand-voice:enforce-voice` or `brand-voice:brand-voice-enforcement`: applies brand guidelines to content. If installed, use it to validate generated text against the user's brand.
- `brand-voice:guideline-generation`: only relevant if the user *doesn't* have brand guidelines yet and wants to build them; do not invoke during a launchkit task.
- `marketing:draft-content` or `marketing:brand-review`: alternative content/brand-review skills. If installed, apply their guidance.

If multiple are installed, apply in this order: brand-voice rules first (they're project-specific), then copywriting (universal quality bar).

**(b) Local brand guideline files in the user's workspace folder.** Look for files matching:

- `brand-voice*.md` / `brand-voice*.txt`
- `voice-and-tone*.md` / `tone-of-voice*.md`
- `style-guide*.md` / `brand-guidelines*.md`
- `messaging*.md` / `brand-book*.md`
- Any file in a `brand/`, `voice/`, or `guidelines/` subfolder.

If found, read them and apply the rules they contain (vocabulary preferences, banned phrases, tone descriptors, target persona, value-prop framings).

**(c) Project context documents** the user has uploaded or referenced in this conversation (Notion pages, briefs, internal docs, marketing positioning files). If present, extract any brand-voice signals: how the brand describes itself, words/phrases it consistently uses, words/phrases it explicitly avoids, target audience persona language.

**Default behavior if nothing is found:**

If none of the above turn up brand context, ask briefly:

> "I didn't find brand voice guidelines in your setup. Do you want me to: (a) draft in a neutral, professional founder voice; (b) match a specific reference (paste a few sentences of your existing copy); or (c) follow a specific tone (e.g., playful / technical / minimalist)?"

If the user picks neutral, default to: clear, specific, conversational-but-professional. No marketing-speak. No AI-cliché phrases ("revolutionary", "game-changing", "in today's fast-paced world", "unlock the power of", etc.).

**State explicitly what was applied.** When delivering the kit(s), include a one-liner near the top:

> *Brand context applied: [what was used, e.g., "copywriting skill (universal quality bar) + style-guide.md from workspace folder"]*

### Step 2 — Hand off to the platform's drafting instructions

For each chosen platform, load and follow `references/<platform>/instructions.md`. That file contains the platform-specific drafting steps (character limits, required sections, image specs, scheduling rules, output format) for that platform.

For multi-platform launches, run the platforms sequentially. After producing the first platform's kit, **before drafting the second platform's kit, briefly cross-reference the first kit's tagline, description hook, and feature ordering** to keep the product story consistent. Each platform's draft adapts the shared story to its specific constraints; it doesn't reinvent it.

### Step 3 — Output structure

Create a per-platform output folder structure under the working directory:

```
<product-name>-launch/
├── producthunt/        ← if Product Hunt is in scope
│   ├── kit.md
│   ├── thumbnail.png   (240×240)
│   ├── gallery-1.png   (1270×760)
│   └── ...
└── uneed/              ← if Uneed is in scope
    ├── kit.md
    ├── logo.png        (≥ 128×128 square)
    ├── image-1.png
    └── ...
```

Each platform folder contains a `kit.md` with all submission fields plus generated visual assets at the platform's required dimensions. The exact `kit.md` structure for each platform is defined in `references/<platform>/instructions.md`.

If the user has a mounted workspace folder, place `<product-name>-launch/` inside that folder. Otherwise place it in the current working directory.

When delivering, list the per-platform folder paths so the user can open them directly.

## Quality checks before delivering

Cross-platform checks (run for every kit produced):

- Brand context check ran. The output explicitly states which sources were applied.
- All output is in English.
- Copy reads in the user's brand voice, not generic AI cliché.
- No links to bit.ly or UTM-tracking URLs anywhere in the submission fields.
- Per-platform output folder exists with `kit.md` + any generated assets.

Platform-specific checks live in each `references/<platform>/instructions.md` under "Quality checks before delivering". Run those for each platform's kit.

## Out of scope

- Launching/submitting forms on the user's behalf. The skill prepares the kits; the user submits.
- Creating accounts on any of the platforms. The user creates accounts themselves.
- Gaming votes or any growth-hacky tactics that violate platform community guidelines.

## References

Cross-platform references this skill loads on demand:

- `references/producthunt/instructions.md` plus `field-requirements.md`, `launch-tags.md`, `image-specs.md`, `first-comment.md`, `shoutouts.md`, `timing-and-scheduling.md`.
- `references/uneed/instructions.md` plus `field-requirements.md`, `categories-and-tags.md`, `image-specs.md`, `timing-and-scheduling.md`.
