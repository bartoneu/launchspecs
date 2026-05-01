# Product Hunt — Timing & scheduling

> ⚠️ **PH's own Launch Guide gives flexibility advice on launch time** ("launch earlier in the day for non-US audiences", "align to press embargo time", "tease the launch and collect followers"). **Most of that flexibility is bad in practice** because it ignores the leaderboard ranking mechanic described below. This reference reflects how PH actually works on launch day, not the marketing-friendly guidance from the public Launch Guide.

## How the daily leaderboard actually works

PH's daily window is **24 hours starting at 12:01 AM PT**. Within that window:

1. **Hours 0–4 (12:01 AM → 4:00 AM PT): randomized homepage sort.** All featured products of the day are shown in **randomized order** — every product gets equal exposure regardless of votes already received. This is PH's "give everyone a chance to be seen" window. Practitioner observation: upvote counts are not visible to visitors during this period either.

2. **At ~4:01 AM PT: the random window ends and the homepage sorts by accumulated votes, descending.** From this point, position on the homepage is dictated by upvotes (and increasingly by engagement signals — see "2026 algorithm changes" below).

3. **Hours 4–24:** the leaderboard updates throughout the day as more votes and engagement come in, but products that already accumulated votes/engagement during the random-sort window have a structural lead.

### Sources for the 4-hour window

The 4-hour figure is **directly confirmed by PH-staff**.

PH's own announcement ([Let's talk about spam](https://www.producthunt.com/stories/let-s-talk-about-spam) by Ashley Higgins, March 23, 2023):

> *"We're testing a randomized homepage sort at the start of the day. This gives all products on the homepage a more distributed chance at exposure early on their launch day. Starting tomorrow, randomization will occur for the **first 2 hours (PT)**…"*
>
> *"**Update:** We have upped the amount of hours the homepage is randomized for to the **first 4 hours (PT)**."*

Cross-validated by independent practitioner sources:

- [Flo Merian's awesome-product-hunt guide](https://github.com/fmerian/awesome-product-hunt/blob/main/product-hunt-launch-guide.md) (42+ launches): *"For the first 4 hours of the day, Product Hunt hides upvotes and sorts the homepage randomly… Your objective is to rank in the Top 5 within that time to maximize exposure."*
- Multiple 2026-vintage launch guides converge on "first 3-4 hours decide the day's trajectory."

### 2026 algorithm changes — engagement now outweighs raw upvotes

Mike Kerzhner (CTO at Product Hunt) and other PH staff have signaled that the 2026 algorithm has shifted weight from raw upvote counts toward engagement signals:

- **Comments and maker replies** matter more than raw votes.
- **Time-on-page** and discussion depth are weighted into ranking.
- **Verified / active users' votes carry more weight** than new or inactive accounts.
- **Threads with replies and ongoing maker participation stay surfaced longer** than pages that get passive upvotes and go quiet.
- The algorithm rewards products that **bring new users to Product Hunt**.

Operational implication: launching at 12:01 AM PT and accumulating early votes is still important, but launch-day **maker engagement** (replying to every comment, asking follow-up questions, having co-makers comment thoughtfully) is now more directly tied to leaderboard position than ever before.

## The only correct launch time

**Schedule for 12:01 AM PST. Period.**

Any later launch:
- Loses some or all of the 4-hour hidden-vote window where exposure is randomized and equal.
- Starts the 4:01 AM PST visible-leaderboard reshuffle **already behind** on votes (because other products had a head start).
- Effectively means starting near the bottom of the visible list right when the homepage starts ranking by votes.

There is no scheduling tactic that compensates for missing the 12:01 AM PST start.

## Schedule horizon

You can schedule a launch up to **1 month in advance**. Use this — booking the slot early reserves it.

Note: PH's older guidance about "tease the launch and collect followers ahead of launch day" is outdated. The launch-tease feature no longer exists. Scheduling early is purely about reserving the date, not about marketing reach beforehand.

## Day of week (independent of time)

Day of week is a real, separate axis from time of day. Pick the day; always launch at 12:01 AM PST on that day.

| Day | Profile | Best for |
| --- | --- | --- |
| **Tue / Wed / Thu** | Heaviest competition; biggest weekday B2B audience | B2B SaaS, dev tools, enterprise products |
| **Mon / Fri** | Slower start (Mon) / earlier checkout (Fri) than mid-week | Generally suboptimal for launches with a choice |
| **Sat / Sun** | Lower competition; **PH-cited +15% Visit clicks** vs. weekdays | Solo makers, side projects, personal apps, consumer products |

For B2B / enterprise / dev-tooling: default to **Tuesday or Wednesday**.

For consumer / solo / side-project: **weekends are often a better tradeoff** — less competition for the leaderboard, and the +15% Visit clicks signals more curious browsing behavior.

## When the user has an external dependency

If the user names a hard external constraint (press embargo with a fixed time that can't move, regulatory announcement, etc.), do **not** treat it as an "alternative scheduling optimization." Treat it as a real cost:

- Tell the user explicitly: *"Launching at [non-12:01 PST time] means you skip part or all of the 4-hour hidden-vote window, and you'll start the visible leaderboard already behind on votes. This is a real cost in launch position. If the embargo can be moved to align with 12:01 AM PST, do that instead."*
- If the embargo genuinely cannot move: launch at the embargo time and brace for a weaker leaderboard position. Don't pretend the choice has no downside.

## Notification asymmetry (operational, separate from timing)

(From the [Help Center](https://help.producthunt.com/en/articles/479557-how-to-post-a-product))

- **Hunter's followers do NOT receive email notifications** about the launch.
- **Maker's followers DO receive an email** IF the launch ends up on the homepage.

Implication: if any team members have substantial PH follower bases, list them as Makers (not just Hunters) so their followers get notified when the launch hits the homepage. This compounds with a 12:01 AM PST start by giving more votes during the critical hidden-voting window.

## Re-launching the same product

If you're submitting the same product within 6 months of a previous launch, special rules apply. See [Launch Guide → Two weeks post-launch → Launching your product again](https://www.producthunt.com/launch/two-weeks-post-launch#launching-your-product-again).

## Quick rule for the skill

```
Schedule = 12:01 AM PST.
Day of week:
  - B2B / enterprise / dev tools → Tue or Wed
  - Consumer / solo / side project → weekend often better
  - Default if unclear → Tuesday at 12:01 AM PST

Hard external dependency (immovable embargo, regulatory date):
  → Launch at the dependency time, but explicitly tell the user the
    cost in starting leaderboard position. Don't frame it as an
    optimization.
```

## What this reference deliberately does NOT recommend

To avoid repeating PH-Launch-Guide errors that cost users votes:

- ❌ Launching later than 12:01 AM PST to align with non-US audience timezones.
- ❌ Launching at press embargo time as a "tactic" rather than a forced tradeoff.
- ❌ "Teasing the launch ahead of time to collect followers" — feature doesn't exist.
- ❌ Recommending Friday launches as a default (slower close-of-week engagement).
- ❌ Any timing tactic that treats deviation from 12:01 AM PST as net-positive.

If a user asks about one of these, explain the leaderboard mechanic and recommend the 12:01 AM PST default.
