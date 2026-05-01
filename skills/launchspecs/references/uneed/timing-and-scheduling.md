# Uneed — timing and scheduling

How the Uneed launch cycle actually works, the scheduling options, and the rolling-leaderboard mechanic that determines what a "successful" launch looks like. Validated against the live `/launch-guide` and `/pricing` pages on 2026-05-01.

## Schedule options

Uneed splits scheduling into three paths, all available from the editor's "Schedule launch" step.

| Option | Price | What it does |
| --- | --- | --- |
| **Join the line** | Free | Auto-assigned to the next available launch slot. Slots fill day by day. |
| **Skip the line** | $29.99 | Pick the exact launch date. Useful when you need to align with a press embargo, a coordinated multi-platform launch, or a date that maps to your audience's habits. |
| **Relaunch** (existing products) | $15 | Re-spotlight a product that has already launched. Free 1×/month with Uneed Pro. |

### When to pay vs. join the line

The free path is fine for most indie launches. Pay $29.99 only if any of these apply:

- You're coordinating with a Product Hunt launch on the same day (cross-platform alignment compounds attention).
- You have a press or newsletter date you can't move.
- The auto-assigned slot lands on a day you know your audience is offline (national holiday in your primary market, weekend for B2B products).

If none of these apply, save the $29.99 for a Newsletter Sponsoring slot ($147) or another paid surface that actually buys reach.

## Best day of the week

Uneed's own Launch Guide recommends **Tuesday through Thursday**. Avoid weekends and major holidays.

| Day | Profile | Best for |
| --- | --- | --- |
| Tue / Wed / Thu | Highest activity, biggest audience for B2B and dev tools | Most launches |
| Mon | Slow start, lower vote velocity | Avoid by default |
| Fri | People check out for the weekend; engagement drops in the second half of the day | Avoid by default |
| Sat / Sun | Lowest activity overall | Avoid for B2B; consumer-facing products with weekend usage habits may make an exception |

Default if unclear: **Tuesday or Wednesday**.

## How the leaderboards actually work

Unlike Product Hunt's strict 24-hour daily window, Uneed runs **four rolling leaderboards** simultaneously: Daily, Weekly, Monthly, Yearly. Votes count whenever they come in, so re-engagement after launch day still moves rankings on the Weekly/Monthly/Yearly boards.

| Leaderboard | Top-3 reward |
| --- | --- |
| Product of the **Day** | Featured on the Uneed homepage on launch day |
| Product of the **Week** / **Month** | Featured in the Uneed newsletter (17,000+ subscribers, ~40% open rate) |
| Product of the **Year** | Year-long traffic boost from being a permanent showcase |

Top-3 placement on any leaderboard earns a permanent **badge** on the product page.

### What this means for launch-day strategy

- The first day still matters most for the Daily leaderboard, but the cost of a quiet launch day is lower than on Product Hunt because the Weekly and Monthly boards re-roll continuously.
- Plan for **post-launch re-engagement**: a follow-up post in your newsletter 4–7 days after launch can move the Weekly leaderboard. A second push at the 3-week mark can land you in top-3 on the Monthly.
- Comment activity on the product page contributes to the page's signal but is not as central as on Product Hunt. Replying to comments is good practice but not the dominant lever.

### Vote multipliers

Uneed Pro members get a **3× vote multiplier**. This affects ranking on every leaderboard. If you're optimizing for a specific leaderboard placement, encourage Pro members in your audience to vote.

## Pre-launch timing

Uneed offers two pre-launch surfaces:

1. **Pre-launch page link.** A `uneed.best/tool/<slug>` URL that goes live before the launch date and collects emails. Share this in advance to build anticipation and seed launch-day votes.
2. **"Launching Soon on Uneed" badge.** An embed code for the product website that links back to the pre-launch page. Both increases traffic to the pre-launch page and signals to your existing audience that a launch is coming.

Recommended pre-launch timeline:

- **2 weeks before launch**: pre-launch page goes live, badge embedded on the product website, first social post.
- **1 week before launch**: second social post, mention in your newsletter, draft the launch-day announcement email.
- **Launch day morning**: send the launch-day announcement email, post to Reddit/IndieHackers/Discord/Slack communities, post on X and LinkedIn.
- **3–5 days after launch**: follow-up newsletter mention to keep Weekly leaderboard activity going.
- **2–3 weeks after launch**: a second push for Monthly leaderboard placement if the product has ongoing relevance.

## Things this reference deliberately does NOT recommend

- ❌ Buying votes or coordinating fake accounts. Uneed has voting moderation and trust signals; gaming the system risks the listing.
- ❌ Submitting a product still in private beta. The URL field requires a working public site.
- ❌ Launching on a weekend by default. Lower traffic, smaller audience, weaker leaderboard signal.
- ❌ Stretching multiple categories. Uneed only allows one category, and stretching tags across irrelevant ones hurts discovery.
- ❌ Treating Skip-the-Line as automatically better. It buys date control, not vote velocity.

## Sources

- [Uneed Launch Guide](https://www.uneed.best/launch-guide)
- [Uneed Pricing](https://www.uneed.best/pricing)
- [How it works](https://www.uneed.best/how-it-works)
