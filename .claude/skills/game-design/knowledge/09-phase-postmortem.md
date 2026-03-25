# Phase 8: POSTMORTEM — Knowledge Reference

Learn what actually happened. Size the next project correctly. Compound the lessons.

---

## The Core Postmortem Question

**Was the goal achieved?**

"Failure depends on the goal": a game that fails by publisher standards can still sustain
a studio if it generates a few hundred dollars/month passively.
**Redefine the success metric before judging an outcome.**

Multiple games generating small passive income is more robust than chasing one hit.
Revenue trends downward without new releases; a single game is a depreciating asset, not a business.

---

## Retention Analysis (Primary Signal)

Retention is the ground truth of product quality. No amount of UA spend fixes a bad D1.

**30-day retention review**:

| Metric | Your Numbers | Genre Benchmark | Gap |
|--------|-------------|----------------|-----|
| D1 | | | |
| D7 | | | |
| D30 | | | |
| Session length avg | | | |
| Sessions/day avg | | | |

**D1 < 25%**: core loop or onboarding is broken
**D7 < 12%**: exit hook or progression is weak
**D30 < 5%**: mid-game content gap or infinite progression without satisfaction endpoint

---

## Revenue Analysis

- **ARPDAU** (revenue per daily active user): are monetized users paying enough?
- **Conversion rate** (free → paying): industry avg 2–5% for F2P; below 1% = offer problem
- **LTV vs. CPI ratio**: if LTV < 2× CPI, UA is not economically viable
- **Top IAP by revenue**: which price point generated most revenue? Inform next game's pricing

---

## Scope Decision Framework (Next Game)

Index next game size to **this game's commercial performance**, not creative ambition:

| Outcome | Next Scope |
|---------|-----------|
| Hit (>2× CPI recovery, strong retention) | +30% larger scope |
| Moderate (broke even, D7 > 15%) | Same scope, different hook |
| Miss (D1 < 30%, LTV < CPI) | Smaller scope; 1 mechanic; 4-6 weeks |
| Never finished | Smallest possible game; define "done" on day 1 |

---

## Shipping Velocity > Code Quality (Calibration)

A clean codebase is only valuable if it increases release rate.
Measure templates by **games shipped**, not code elegance.

Shipping a game matters more for what it **teaches** than what it earns.
The skills compound into future work. Failure of a first project is a normal career stage.

Build toward a reusable template:
- After this project: strip game logic, keep menu/UI/save scaffolding
- Next project starts with working infrastructure, not blank canvas
- Template investment pays off at game 3+

---

## The Three Traps Review

Look back at this project and identify which trap you fell into:

1. **Manifestation trap**: consuming aspirational content with no shipping
   (watching game dev YouTube instead of making the game)
2. **Distraction trap**: solving problems you didn't have yet, causing restarts
   (spent 2 weeks on an inventory system before validating the core loop)
3. **Inaction trap**: learning the right things in the right order but never shipping
   (kept prototyping, never committed to production)

Diagnosis → specific behavior change for next project.

---

## Solo Dev Quit Pattern (Avoid Next Time)

The solo dev quit trigger is not boredom — it's **mid-refactor breakage**:
you quit when a structural change cascades across the whole codebase
and motivation is already declining.

Prevention for next project:
- Budget for "The Wall" (motivation drop when game looks worse than imagined)
- Rule: do not restart — scope down and cut features, but finish
- Daily commits: worst-case rollback = one day's work
- Define "done" on day 1 with a written checklist

---

## What Worked / What Didn't (Structured Review)

Categories to review:

| Area | What Worked | What Didn't | Change Next Time |
|------|------------|-------------|-----------------|
| Concept clarity | | | |
| Scope management | | | |
| Prototype speed | | | |
| Playtest timing | | | |
| Launch marketing | | | |
| Monetization | | | |
| Technical pipeline | | | |
| Polish allocation | | | |

---

## Career / Skill Compounding

Each project should target **one skill** to level up:
- First game: shipping discipline (finishing)
- Second game: feel & feedback layer
- Third game: monetization integration
- Fourth game: UA and market validation

Write your dream game in one paragraph. List required skills. Pick ONE to focus on per game.
The dream game's job is to generate a skill roadmap, not to be made yet.

---

## Postmortem Output Artifact

```
POSTMORTEM REPORT
─────────────────────────────────────
Game title:
Launch date:
Defined success metric (from Phase 2):

PERFORMANCE SUMMARY:
  D1 retention: ___% (benchmark: 35%+)
  D7 retention: ___% (benchmark: 18%+)
  D30 retention: ___% (benchmark: 8%+)
  Total installs (first 30 days):
  Revenue (first 30 days): $___
  LTV estimate: $___
  CPI (if UA run): $___
  Success metric: [ ] achieved  [ ] partially  [ ] missed

RETROSPECTIVE:
  Three things that worked:
  Three things that didn't:
  Which trap: [ ] Manifestation  [ ] Distraction  [ ] Inaction  [ ] None

SCOPE CALIBRATION:
  Actual build time vs. estimate:
  Scope creep instances:
  What should have been cut:

SKILL TARGETED THIS PROJECT:
SKILL ACHIEVED:
NEXT SKILL TO TARGET:

NEXT PROJECT DECISION:
  Scope: [ ] smaller  [ ] same  [ ] larger
  Model: [ ] same genre  [ ] same mechanic/new skin  [ ] new concept
  Timeline: ___ weeks
  "Done" definition (written now, before starting):

TEMPLATE EXTRACTED:
  Reusable systems from this project:
  Scaffolding kept for next project:
─────────────────────────────────────
```
