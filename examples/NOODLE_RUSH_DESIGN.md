# Noodle Rush — Game Design Document

**Version:** 0.4
**Status:** Phase 4 Plan Complete — awaiting prototype results

---

## Phase 1: CONCEIVE ✓

### Concept Card

```
CONCEPT CARD — Noodle Rush
─────────────────────────────────────────────
Title:               Noodle Rush
Core verb:           Pipeline, position, clear
Appeal type:         [x] Toy  [x] Puzzle
Anchor:              Pixel Flow clearing + Block Blast pipeline management
Comparables:         Pixel Flow, Block Blast!, Royal Match
Theme:               Kitchen / noodle & dumpling characters (original IP)
Mobile:              Portrait, one-thumb, pause-safe, <4 min sessions

HOOK:
  Misplaced characters return to the conveyor with leftover
  clearing power. The pipeline has a hard limit. Inefficient
  play clogs your own kitchen — and ends the rush.

CORE CONSTRAINT:
  Sum of all character numbers = total grid blocks by color.
  Every level is always solvable. Skill = zero wasted clearing.

WIN:   All noodle blocks cleared from bowl grid.
FAIL:  Waiting line overflows ("Kitchen Overflow!").
─────────────────────────────────────────────
```

### System Architecture

```
3-LINE QUEUE  (auto-fills — source of all characters)
      ↓  player taps to pull
WAITING LINE  (player staging — limited capacity, overflow = fail)
      ↓  player taps to promote
CONVEYOR      (max 5 — loops around bowl grid perimeter)
      ↓  player moves conveyor to position character
      →  auto-fires when adjacent to matching color tile
      →  flood-clears connected same-color blocks up to N
      →  if cluster < N: returns to conveyor with remainder
```

### Player Decision Layers

| Zone | Decision |
|---|---|
| 3-line queue → waiting line | Which characters to pull, when |
| Waiting line → conveyor | Which to promote, in what order |
| Conveyor movement | Where to position each character around grid |

### Four-Part Test

| | |
|---|---|
| **Win** | All noodle blocks cleared |
| **Obstacle** | Hard capacity at every zone; bounced characters add congestion |
| **Fail** | Waiting line overflows |
| **Actions** | Pull → stage → load conveyor → position to auto-fire |

### Mobile Filters
- One-thumb portrait: ✓
- Session fit (<4 min): ✓
- Interruption-safe: ✓
- No precision aiming: ✓ (auto-fire on adjacent match)

### Phase 1 Gate: PASSED ✓

---

## Phase 2: VALIDATE ✓

### Validation Report

```
VALIDATION REPORT — Noodle Rush
─────────────────────────────────────────────
MARKET CHECK

  Top comparables:
  1. Pixel Flow        — direct mechanic reference; top chart casual;
                         mostly positive; 1-star: "too many forced ads",
                         "levels feel the same after 30", "no story hook"
  2. Block Blast!      — pipeline hand management anchor; massive install
                         base; 1-star: "no character identity", "gets
                         boring fast", "no meta progression"
  3. Royal Match       — audience size benchmark; 1-star: "pay wall too
                         early", "lives system too punishing"

  Gap identified:
  - No top-chart game combines Pixel Flow's flood-clear with
    a named character cast and kitchen meta narrative.
  - Pixel Flow has no character identity — no one to collect.
  - Block Blast has no theme — pure abstraction, poor D30.
  - Kitchen/food theme is underrepresented in puzzle top charts.

MONETIZATION FIT
  Model:        [x] F2P hybrid (Coins IAP + Season Pass + Rewarded Ads)
  Touchpoints:
    - Kitchen Overflow: pay coins to clear waiting line (high urgency)
    - Bounce rescue: watch ad to re-route a bounced character
    - Level failed: watch ad OR coins to continue
    - Season Pass ~$4.99/mo: exclusive seasonal skins + coin bonus
  LTV estimate: $1.50–$3.00 (casual F2P benchmark)
  Target CPI:   <$2.00 (casual puzzle; food theme aids creative CTR)
  Fit verdict:  ✓ Session pattern (short loops, overflow moments)
                  supports all three monetization triggers naturally.

SCOPE CHECK
  Core loop prototype:  1–2 weeks (conveyor + grid + auto-fire)
  Full project (MVP):   4–8 months (core + 60 levels + economy)
  Scope verdict:        ✓ Appropriate for small team (2–4 people)
  Note: 3-zone pipeline is the main implementation complexity.
        Prototype zone 2→3 transition first — highest-risk mechanic.

ICON / STORE PAGE
  First screenshot:     Cute dumpling character on conveyor belt,
                        colorful noodle grid, number visible on character.
  Hook visible in icon: ✓ Character + noodle bowl communicates
                          theme and casual puzzle genre immediately.
  UA creative (3 sec):  Show character traveling conveyor →
                        landing near grid → noodles slurped away.
                        Satisfying clear animation IS the ad.

ASSUMPTION FLIP
  Genre convention challenged:
  Every puzzle game has the player interact DIRECTLY with the
  board. Noodle Rush mediates all interaction through a pipeline —
  you never touch the grid, only position the delivery system.
  The board solves itself when you manage the pipeline correctly.

ONE DIFFERENTIATOR (single strongest):
  The pipeline IS the puzzle. Not the grid.

DONE CHECKLIST (pre-build gates)
  [ ] Core loop playable start-to-finish (3-zone → grid clear)
  [ ] Win state: all blocks cleared
  [ ] Fail state: waiting line overflow triggers correctly
  [ ] Session length: 2–4 min per level
  [ ] Bounce-back mechanic: character returns with remainder
  [ ] Monetization: overflow + bounce rescue IAP/ad triggers defined
  [ ] Store page: icon + 3 screenshots designed before global launch

GATE DECISION: [x] ADVANCE TO DESIGN
─────────────────────────────────────────────
```

### Theme & Colors

| Color Name | Block Color | Character |
|---|---|---|
| Ramen Red | Pink/Red | Gyoza Gary |
| Udon Blue | Cyan/Blue | Udon Uma |
| Matcha Green | Green | Matcha Mochi |
| Curry Yellow | Yellow/Orange | Curry Kuma |
| Squid Ink | Black/Purple | Squid Suki |

Special characters (Wildcard, Doubler, Column clear, Full-color clear) — scope for v2 or post-launch.

### Phase 2 Gate: PASSED ✓

---

## Phase 3: DESIGN ✓

### Design Document

```
DESIGN DOCUMENT — Noodle Rush
─────────────────────────────────────────────
Game title:    Noodle Rush
Core verb:     Pipeline, position, clear

DESIGN PILLARS (how players feel)
  1. "I feel like a clever kitchen manager" —
     routing the right ingredient to the right place at the
     right time. [Application of ability + Intellectual problem solving]
  2. "I feel the tension of a kitchen about to boil over" —
     the pipeline pressure creates genuine stakes.
     [Thrill of danger]
  3. "I feel satisfied by a clean, effortless clear" —
     the visual and audio of noodles slurped away.
     [Beauty + Toy appeal]

5 FUNDAMENTALS CHECK
  Tension:     Pipeline hard limits + bounced characters + overflow risk ✓
  Agency:      Player controls all 3 zones; choices have direct consequence ✓
  Clarity:     Number on character = blocks cleared; auto-fire = predictable ✓
  Progression: Grid visibly empties per action; level counter advances ✓
  Resolution:  Slurp animation + audio + level complete screen (triple signal) ✓

CORE LOOP
  Action:      Tap to move character through pipeline zones;
               position conveyor to face matching color cluster
  Feedback:    Auto-fire triggers instantly (<100ms); flood animation plays
  Reward:      Blocks slurped away; character number depletes visibly;
               "slurp" SFX + particles + block count update
  Next action: More blocks visible; queue shows next characters;
               waiting line position telegraphs overflow risk
  Duration:    2–4 min per level

SESSION ARC
  Cold start:  Grid + queue visible immediately on load;
               first character highlighted; no tutorial text
  Loop reps:   5–15 pipeline actions per level; 3–5 levels per session
  Escalation:  Grid density + color count increases mid-level;
               bounce characters re-enter and add pressure
  Exit hook:   Level end → "Next level" grid shape teased +
               daily bowl challenge banner visible
  Sessions/day: 4–6 (casual; natural stop = level complete)

PROGRESSION
  Milestones:  World 1 (L1–20) → World 2 (L21–50) → World 3 (L51–100)
               Each world = new grid shapes + new color combos introduced
  Mastery:     "Perfect Rush" (zero bounces), "Speed Bowl" (under par time),
               "No Coins" (no IAP/ad used)
  Memento:     Restaurant decoration meta — coins spent between levels to
               upgrade your kitchen. Visible proof of progress.
               [Addresses Block Blast's D30 failure: no meta = churn]

MONETIZATION (designed into loop, not bolted on)
  Model:       F2P — Coins IAP + Season Pass + Rewarded Ads
  Trigger 1:   Kitchen Overflow imminent (waiting line 80% full) →
               "Clear 3 spots — 50 gems" — highest urgency, mid-session
  Trigger 2:   Bounced character causing cascade →
               "Watch ad: send it back for free" — player-initiated
  Trigger 3:   Level failed → "Watch ad OR 30 coins to continue"
  Trigger 4:   Season Pass ($4.99/mo) — ambient; exclusive skins +
               daily coin bonus + ad-free play
  First IAP:   $0.99 starter pack (200 coins + exclusive skin) —
               introduced after first level fail (~level 12–15)
  Ad rule:     Player-initiated only; never mid-action; max 5/day rewarded

DILEMMA TYPES PRESENT
  [x] Scarcity   — limited conveyor slots; limited waiting line capacity
  [x] Trade-off  — use big character on small cluster (waste) vs.
                   wait and risk overflow (danger)
  [ ] Prediction — not in v1; multiplayer consideration for v2

LEVEL TYPES (introduced one at a time)
  Standard:     Clear all blocks. L1–10.
  Rush:         Waiting line fills faster. L20+.
  Color Lock:   One color frozen — specific character type required. L30+.
  Limited Hand: Conveyor max 3 (not 5). L45+.
  Boss Bowl:    Oversized grid, guaranteed rare characters, flashy clear. L20/50/100.

SCOPE
  Systems:      3 core (pipeline, grid clearing, bounce-back)
                + 1 meta (restaurant decoration)
  Content:      Hybrid — authored levels L1–100; systemic beyond L100
  v1 target:    100 authored levels + 5 character types + 1 season
  Build target: 4–8 months (small team 2–4)
  Scope filter: "Not a restaurant sim. The restaurant is the scoreboard."

─────────────────────────────────────────────
```

### Open Question — Meta Progression Depth

One decision deferred to prototype validation:

**Restaurant decoration meta** (like Royal Match's castle):
- Coins from levels → spend to upgrade kitchen visuals
- Serves D30 retention; gives players a reason to return beyond level number
- Risk: adds 4–6 weeks of art scope

Validate in Phase 5 (Playtest): if D7 drop-off is sharp without it, add meta.
If D7 holds on core loop alone, ship without and add post-launch.

### Phase 3 Gate: PASSED ✓
- [x] Pillars defined (3, player-experience statements)
- [x] Loop spec written (Action → Feedback → Reward → Next)
- [x] Session architecture complete
- [x] Monetization integrated (3 in-loop triggers + Season Pass)
- [x] Scope bounded (100 levels, 3 systems, 4–8 months)

---

## Phase 4: PROTOTYPE ✓

### Prototype Plan

Phase 4 defines what to build, in what order, and how to know if it worked.
Actual results fill in after each prototype run.

---

#### Risk Register (priority order)

| # | Risk question | Why it matters |
|---|---|---|
| 1 | Is managing 3 zones on a phone screen intuitive? | Core UX — too much UI kills casual audience |
| 2 | Does auto-fire feel intentional or random? | Players must feel in control even when the game fires itself |
| 3 | Does bounce-back create tension or feel punishing? | The hook mechanic — if it feels unfair, the whole concept fails |
| 4 | Does overflow pressure arrive early enough to feel predictable? | Fail state must never feel sudden or invisible |
| 5 | Is level design (equal by design constraint) fast to author? | If building levels takes > 1 day each, scope collapses |

---

#### Prototype 1 — Zone Navigation (Start Here)

```
PROTOTYPE 1
─────────────────────────────────────
Question:    Can a player move a character through all 3 zones
             in under 5 taps without instructions?
Medium:      Figma / paper mockup first → engine second
Included:    3-line queue UI, waiting line UI, conveyor UI,
             tap-to-move interactions between zones
Excluded:    Grid, block clearing, bounce-back, any art

10-second test:
  Show mockup to 2 people. Ask them to "send this character
  to the conveyor". Count taps. Watch where they tap first.
  Success: they find the path without asking.
  Fail: they tap the wrong zone or ask what to do.

Success criteria:
  - 3 out of 3 testers move a character to the conveyor
    without instruction on first attempt
  - Tap count ≤ 3 per zone transition

Result:      [ ] pass  [ ] fail  [ ] redesign zone layout
─────────────────────────────────────
```

#### Prototype 2 — Auto-fire Feel (Core Loop)

```
PROTOTYPE 2
─────────────────────────────────────
Question:    Does auto-fire + flood clear feel satisfying
             and intentional on a real device?
Medium:      Unity (engine) — must be on device, not editor
Included:    Conveyor movement, auto-fire trigger, flood-clear
             animation, "slurp" placeholder SFX, 1 color only
Excluded:    Multiple colors, bounce-back, pipeline zones,
             UI, economy — grey boxes only

10-second test (on device):
  Load prototype. Move conveyor. Watch character fire.
  Does it feel like YOU did that?
  Does the clear animation invite you to do it again?

Success criteria:
  - Tester says "satisfying" or "again" unprompted
  - Auto-fire trigger feels like result of player action,
    not random event
  - Clear animation completes in < 800ms (not too slow)

Result:      [ ] pass  [ ] fail  [ ] tweak trigger timing
─────────────────────────────────────
```

#### Prototype 3 — Bounce-back + Overflow Tension

```
PROTOTYPE 3
─────────────────────────────────────
Question:    Does bounce-back create "oh no" tension or
             "that was unfair" frustration?
Medium:      Engine — extend Prototype 2
Included:    Bounce-back logic (character returns with N
             remainder), waiting line with visible capacity,
             overflow fail state, 2 colors on grid
Excluded:    Season pass, economy, level progression,
             onboarding, art

Key test:
  Let 3 testers play to overflow. After each:
  Ask "did you see that coming?"
  Ask "could you have prevented it?"
  Success: both answers are yes.
  Fail: either answer is no → UI needs earlier warning signal.

Success criteria:
  - Overflow never feels sudden (warning signal lands 3+ moves early)
  - Bounced character returning feels logical, not buggy
  - At least 2/3 testers attempt a second run after failing

Result:      [ ] pass  [ ] fail  [ ] adjust warning timing
─────────────────────────────────────
```

#### Prototype 4 — Level Authoring Speed

```
PROTOTYPE 4
─────────────────────────────────────
Question:    Can a level designer (or solo dev) create a
             valid "equal by design" level in < 30 minutes?
Medium:      Spreadsheet or simple editor tool
Included:    Grid layout tool, color placement, auto-sum
             validator (confirms total blocks = total character
             numbers), export to game format
Excluded:    Everything else

Success criteria:
  - 5 levels authored in 1 day
  - Equal-by-design constraint verifiable in 1 click
  - Grid shapes feel visually varied without manual effort

Result:      [ ] pass  [ ] fail  [ ] build level editor tool
─────────────────────────────────────
```

---

### Prototype Sequence Rule

> **Do not start Prototype 2 until Prototype 1 passes.**
> Zone navigation is the foundation. A fun clear animation
> means nothing if players can't figure out how to trigger it.

### Phase 4 Gate (fill in after prototyping)
- [ ] 3-zone UI navigable without instruction (P1)
- [ ] Auto-fire feels intentional on device (P2)
- [ ] Bounce-back tension confirmed positive (P3)
- [ ] Level authoring is fast enough to ship 100 levels (P4)

---

## Phase 5: PLAYTEST

_To be completed._

---

## Phase 6: POLISH

_To be completed._

---

## Phase 7: LAUNCH

_To be completed._

---

## Phase 8: POSTMORTEM

_To be completed._
