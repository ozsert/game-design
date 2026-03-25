# Phase 2: VALIDATE — Knowledge Reference

Stress-test the concept before building anything. On mobile, validation is cheap; a bad launch is expensive.

---

## Trailer Mental Model (Validate Before Prototype)

Lucas Pope: won't pursue an idea he can't imagine a cool trailer for.
Tom Francis: validates by working out the **store page name and icon art** before writing code.

Mobile equivalent:
- Can you describe the **first screenshot** in one sentence?
- Does that screenshot communicate the core loop AND the genre anchor?
- Would someone scroll past it or tap it?

If you can't design the icon before building the game, the concept isn't clear enough yet.

---

## Cover Art Signal Test

Cover / icon art must signal the **gameplay loop**, not just the genre:
- Lone character on cliff = exploration
- Multiple characters doing different things = social/town-building
- Action pose underground = roguelike
- Bright colors + candy/gems = casual match
- Timer + stress = puzzle under pressure

Test: show the icon to 5 people who haven't heard of the game.
Ask: "What do you do in this game?" Their answer tells you if the signal is working.

---

## Scope Reality Check (Prototype Time Rule)

Jonas Tyroller's rule of thumb:
- Gameplay prototype in 1–2 days → game can be made in 1–2 years
- Prototype takes 2 weeks → full project will be very long

Mobile application:
- Core loop prototype in < 1 week → viable scope for 2–6 month mobile project
- First playable on device in < 2 weeks → scope is controlled
- If you can't hold the loop in your head in full detail → it's too complex

---

## Scope Decision Framework

Size of next game should be indexed to **prior game's commercial performance**, not creative ambition:
- No shipped game yet → smallest viable scope (1 mechanic, 20 levels)
- First game shipped → similar scope or slightly larger
- First game hit → bigger scope justified

Treat first game as a learning exercise: ship, learn conversion rates, apply lessons.

---

## Mobile Market Validation

Before committing to a concept, answer:

**Comparable analysis**:
- Name 3 games on the App Store with the same core mechanic
- What are their ratings and review counts? (proxy for market size)
- What do their 1-star reviews complain about? (gap to fill)
- Are the top games in this category 3+ years old? (underserved) or 6 months old? (hot)

**CPI benchmark check**:
- Hyper-casual: CPI < $1 required for ad-monetized profitability
- Casual F2P: CPI < $3 with D30 ROAS > 100%
- Mid-core: CPI up to $15 acceptable with high LTV
- If your genre's average CPI exceeds your monetization model's LTV → structurally unprofitable

**Monetization model fit**:
Ask: does the session pattern support the monetization?
- Lives/energy systems require D7+ retention to monetize; useless if D1 is 20%
- Gacha requires strong social hooks to drive competitive spending
- Premium requires a strong hook that survives the paywall decision
- Ad monetization requires high DAU volume; doesn't work at small scale

---

## Hook + Anchor Test (Applied)

Write one sentence pitch: "[familiar game] meets [twist]"

Test against three failure modes:
1. **Too familiar**: pitch could describe an existing top-chart game exactly → no room
2. **Too novel**: person hearing pitch has no mental model → no anchor
3. **Feature list masquerading as hook**: "It has 50 levels and 10 characters" → no hook

Strong hook: makes the listener immediately ask a question ("Wait, what happens when...?")

---

## The Flawed Assumption Check

Challenging a genre's conventions means identifying the implicit assumption nobody questions:
- Every board game resets (Rob Daviau) → what if it didn't? → Risk Legacy
- Every mobile puzzle has unlimited time → what if each move costs seconds?
- Every idle game accumulates while offline → what if it decays instead?

Ask: "What does everyone in this genre take for granted that I could remove or invert?"
One strong assumption flip is worth more than ten feature additions.

---

## Define Done (Before Building)

Write a "done checklist" before touching code:
- [ ] Game is playable from start to finish
- [ ] Player can win and lose
- [ ] Core loop completes in < N minutes
- [ ] Store page (icon + 3 screenshots) is designed
- [ ] Monetization model is defined

Without this, finishing is impossible because the target keeps moving.

---

## Validate Output Artifact

```
VALIDATION REPORT
─────────────────────────────────────
Concept Card: [from Phase 1]

Market check:
  Top 3 comparable games:
  Their ratings / review counts:
  Gap identified (what 1-star reviews ask for):

Monetization fit:
  Model: [ ] F2P  [ ] Premium  [ ] Paymium  [ ] Ads
  LTV estimate: $___
  Target CPI: $___  (must be < LTV / 12 months)

Scope check:
  Core loop prototype time estimate: ___
  Full project time estimate: ___
  Scope vs. experience level: [ ] appropriate  [ ] too large

Icon/store page mental model:
  First screenshot description:
  Hook visible in icon: [ ] yes  [ ] no

Assumption flip (optional):
  Genre convention being challenged:

Done checklist (written before build):
  [ ] playable start-to-finish
  [ ] win + lose states defined
  [ ] session length target: ___ min
  [ ] monetization integrated (not bolted on)

GATE DECISION: [ ] ADVANCE TO DESIGN  [ ] RETURN TO CONCEIVE
─────────────────────────────────────
```
