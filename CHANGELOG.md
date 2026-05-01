# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2026-04-29

### Added

- Initial release.
- `skills/launchspecs/`: thin orchestrator skill. Identifies target launch platform(s) from the user's request via AskUserQuestion, lazy-loads only the relevant platform references, applies brand-voice context, and writes per-platform output folders (`<product-name>-launch/<platform>/`) containing a `kit.md` plus generated visual assets at platform-required dimensions.
  - `SKILL.md`: orchestrator instructions covering platform identification, context gathering, brand-voice integration, hand-off to platform-specific drafting, and output structure.
  - Platform-specific drafting lives in `references/<platform>/instructions.md` so adding a new platform doesn't touch the orchestrator.
- `references/producthunt/`: full Product Hunt support.
  - `instructions.md`: drafting guide (text fields, first-comment scaffold, image generation, scheduling, output structure, quality checks).
  - `field-requirements.md`: every form field with its hard constraint, sourced from the live form and PH-official documentation.
  - `launch-tags.md`: full enumerated list of accepted Launch tags (419 total, 249 top-level + 170 sub-tags).
  - `image-specs.md`: thumbnail and gallery dimensions, formats, design briefs.
  - `first-comment.md`: first-comment guidance with the PH AI-comment ban handled explicitly (scaffold-only output).
  - `shoutouts.md`: Shoutouts mechanics and selection strategy.
  - `timing-and-scheduling.md`: when to launch, day-of-week tradeoffs, the 4-hour hidden-vote window, 2026 algorithm shift to engagement signals.
- `references/uneed/`: full Uneed support.
  - `instructions.md`: drafting guide (text fields, image generation, scheduling, post-launch re-engagement plan, output structure, quality checks).
  - `field-requirements.md`: every editor field with its constraint, plus the pre-launch ops checklist.
  - `categories-and-tags.md`: 5 categories (single-select) and 185-tag global pool (multi-select).
  - `image-specs.md`: logo, images, and launch-video specs with design briefs.
  - `timing-and-scheduling.md`: schedule options (Free / Skip-the-Line / Relaunch), best days, rolling-leaderboard strategy.
- `LICENSE`: MIT.
- `README.md`: project overview, architecture, output structure, installation, usage.
- `.gitignore`: standard system, editor, and working-directory exclusions.

### Notes

All platform constraints validated against live forms and platform-official sources as of 2026-04-29 (Product Hunt) and 2026-05-01 (Uneed).
