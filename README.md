# launchspecs

One AI skill that turns your product context into complete, submission-ready launch kits for indie launch platforms. v1.0.0 covers **Product Hunt** and **Uneed**. Peerlist and BetaList come next.

> ⚠️ **Unofficial, community-maintained.** Not affiliated with, endorsed by, or sponsored by Product Hunt, Uneed, or any other launch platform.

## The problem this solves

It's launch week. You open the Product Hunt submission form. The tagline field has a 60-character limit you keep hitting. The category selector shows 419 options. The gallery wants exactly 1270×760. The first-comment field is "Strongly Recommended" but the help text doesn't say what makes a strong one. Then you remember you wanted to launch on Uneed too. Different limits there (tagline ≤80), different category taxonomy, different image specs, different scheduling logic. You start a chat with Claude or Cursor and spend 40 minutes ping-ponging through "wait, what's the limit again?" and "what categories exist?" and "what size were the screenshots?" once for each platform.

The AI has all the context about your product. It just doesn't know the platforms' current state. So you become a human relay between two systems that should be talking directly.

This skill closes that loop. It loads every platform constraint as structured reference data your AI agent can use without asking. You give it your product brief or a link to your landing page, you pick which platforms you're launching on, and you get back a complete kit per platform: name, tagline options, description, categories or tags, image specs, scheduling guidance, any platform-specific artifacts (Product Hunt's first-comment scaffold, Uneed's deal block), plus a pre-launch ops checklist.

If you're launching on multiple platforms in the same week, one invocation produces all kits with cross-aligned copy: same product story, platform-specific adaptation per each platform's constraints.

## How it's organized

One skill, one orchestrator file, one folder per platform. Lazy-loaded references keep the context window small.

```
launchspecs/
└── skills/
    └── launchspecs/
        ├── SKILL.md                          ← thin orchestrator
        └── references/
            ├── producthunt/
            │   ├── instructions.md           ← drafting guide for PH
            │   ├── field-requirements.md
            │   ├── launch-tags.md
            │   ├── image-specs.md
            │   ├── first-comment.md
            │   ├── shoutouts.md
            │   └── timing-and-scheduling.md
            └── uneed/
                ├── instructions.md           ← drafting guide for Uneed
                ├── field-requirements.md
                ├── categories-and-tags.md
                ├── image-specs.md
                └── timing-and-scheduling.md
```

The orchestrator's first step is to ask which platform(s) you're targeting. It then loads only the references for those platforms. A Product Hunt-only launch never pulls Uneed data into context.

When new platforms land (Peerlist, BetaList), each gets its own `references/<platform>/` folder with an `instructions.md` and any platform-specific reference files. Same skill, more coverage.

Verified against the live forms and platform documentation as of 2026-05-01 (Uneed) and 2026-04-29 (Product Hunt).

## Output structure

The skill writes one folder per platform under your working directory:

```
<your-product>-launch/
├── producthunt/          ← if Product Hunt is in scope
│   ├── kit.md            ← all submission fields, scaffold, schedule
│   ├── thumbnail.png     ← 240×240
│   └── gallery-1.png     ← 1270×760, hero card
└── uneed/                ← if Uneed is in scope
    ├── kit.md            ← all editor fields, schedule, post-launch plan
    ├── logo.png          ← square ≥ 128×128
    └── image-1.png
```

Each platform's `kit.md` matches its submission flow exactly: paste-ready fields in the order you'll fill them out. The visual assets are sized to the platform's requirements so you don't re-export anything.

## Install in 60 seconds

Clone the repo, then copy the skill folder into your AI tool's skills directory.

```bash
git clone https://github.com/bartoneu/launchspecs.git
cp -r launchspecs/skills/launchspecs ~/.claude/skills/
```

This works for Claude Code, Cowork, and any other tool that reads skills from `~/.claude/skills/`. Restart your tool and the skill is available.

If you'd rather not clone the whole repo, you can download just the `skills/launchspecs/` folder from GitHub.

## How to use it

In your AI tool, ask for a launch kit:

> Prep a Product Hunt launch for my product. Pull context from `landing-page-copy.md` and the brief I uploaded.

Or for multiple platforms in one go:

> Launch this on Product Hunt and Uneed. Use the brief in my workspace folder.

The skill confirms target platforms with a quick AskUserQuestion (so you can add or change platforms after seeing what's supported), then looks for product context (uploaded files, your workspace folder, a Notion link if you provide one, or the product's live website if you give a URL). It only asks you for what it can't find on its own.

A live example output and screenshots will land here after the first dogfooded launch. For now, the skill itself is the artifact. Read `skills/launchspecs/SKILL.md` and the platform `instructions.md` files to see exactly what it does.

## Roadmap

Next platforms in line: Peerlist and BetaList. Each lives in its own `references/<platform>/` folder under the same skill, so the full launch sequence runs through one invocation.

If you want a specific platform prioritized, open an issue with a link to its submission form and a short note on why.

## Contributing

PRs welcome, especially for:

- Constraint updates when a platform changes its form. Date the change in `CHANGELOG.md`.
- New platform support following the existing structure: `references/<platform>/instructions.md` (drafting guide) plus the data references the platform needs (field requirements, taxonomy, image specs, scheduling).
- Corrections to any cited source. Tag the source URL and the correct value.

For larger changes, open an issue first to align on direction. This is a small project and I want to keep it focused.

## A note on the platforms this covers

This skill exists to help makers do better launches, not to game any system. It refuses to generate turnkey first comments for Product Hunt (PH bans LLM-generated comments and will hide them). It doesn't recommend vote-gaming tactics for any platform. It doesn't automate form submission. The goal is to remove the platform-knowledge bottleneck so you can spend your prep time on the parts that actually matter: a sharp product story, real maker engagement on launch day, and follow-through.

If you're at any of the covered platforms and want something addressed in this repo, open an issue or email me through my GitHub profile.

## License

MIT. See [LICENSE](LICENSE).
