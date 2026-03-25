# Phase 3: DESIGN — Knowledge Reference

Translate the validated concept into a concrete design. Produce pillars, core loop spec, and system design.
No engine work yet.

---

## Design Pillars (Operational Definition)

1. Pick 2–3 forms of fun from Garnier's 14 (see 00-core-principles.md)
2. Write each pillar as a player-experience statement:
   - "Players feel like a clever predator"
   - "Players feel the thrill of near-misses"
   - "Players feel pride in their constructed system"
3. Every mechanic decision gets evaluated: "Does this serve a pillar?"
4. If a mechanic serves none of the pillars → cut it

SOMA design pillars example: "trust the player" + "everything is story"
These derive from immersion + intellectual problem solving — two Garnier forms.

---

## Core Loop Design

The core loop is the **action the player takes 100 times per session**.

Structure it as: **Action → Feedback → Reward → Next Action**

Mobile core loop checklist:
- [ ] Loop completable in < 3 minutes (casual) or < 10 minutes (mid-core)
- [ ] Feedback is immediate (< 100ms visual response to input)
- [ ] Reward has audio + visual + progression signal (triple response)
- [ ] Next action is obvious without tutorial instruction
- [ ] Can be interrupted at any point (pause-safe)

### Core Loop Depth Test
Play the loop 10 times in your head. Does it:
- Get boring by rep 3? → too shallow; add a variable or decision
- Get confusing by rep 3? → too complex; reduce to one verb
- Create a "one more time" pull? → correct

---

## Session Architecture (Mobile-Specific)

Design the full session arc, not just the loop:

```
[Session Start]
  → Immediate engagement hook (reward for returning, or resume mid-action)
  → Core loop × N repetitions
  → Escalating tension or challenge
  → Natural stopping point (level clear, resource depleted, boss defeated)
  → Reward reveal (the reason to open the game tomorrow)
[Session End]
```

Mobile session design rules:
- **Cold start**: first 15 seconds must give player something to do, not read
- **Warm start** (returning player): show progress made since last session first
- **Exit hook**: always end on an open loop (near-complete objective, pending reward)
- **Session count target**: design for 3–5 sessions/day for casual, 1–2 for mid-core

---

## Monetization as Design (Not a Bolt-On)

Monetization must be designed into the loop, not added after:

**Energy/Lives model**:
- Works: when the game creates strong "one more try" desire
- Fails: when sessions are long (players quit instead of paying to continue)
- Design: each life = one attempt at a core loop; fail states consume lives

**Battle Pass / Season model**:
- Works: when you have consistent content update cadence (weekly/monthly)
- Fails: for solo devs without update pipeline
- Design: progression visible on the main screen; seasonal goals in the HUD

**Rewarded ads model**:
- Works: when player is stuck or just missed a goal
- Design: offer ad at the exact moment of near-miss ("Watch ad to continue?")
- Never: force ads mid-session; player-initiated only

**Gacha / Lootbox model**:
- Works: with strong collectible identity (characters, skins) + social comparison
- Fails: without a social layer or without cosmetically distinct pulls
- Design: pity system required (guaranteed rare after N pulls); ban in some markets

**IAP pricing psychology**:
- First IAP offer at $0.99–$2.99 (low barrier to first purchase)
- Anchor with a high-value pack (makes mid-tier look reasonable)
- Starter pack (limited-time): highest conversion rate IAP type

---

## Dilemma Triangle

Design decisions around three dilemma types (at least one must be present):

1. **Scarcity**: limited picks/resources force meaningful choice
2. **Trade-off**: every option has an upside and downside bundled together
3. **Prediction**: simultaneous decisions against an opponent or system

Without at least one dilemma type, "choices" in the game are illusions.

Mobile application: scarcity is the most tractable (limited moves, limited time, limited inventory).

---

## Progression Architecture

Three types — combine for depth:

- **Milestones**: fixed reference points you can surpass (level 50, world 3)
- **Mastery challenges**: concrete tests proving skill growth ("beat without losing a life")
- **Mementos**: persistent proof of effort (costume made from enemy you defeated, badge, trophy)

**Mementos outperform stat increases** as satisfaction drivers.
A castle you built beats equipment you equipped because only one exists visibly.

**Infinite progression is structurally incompatible with satisfaction**.
The feeling of "job done" requires an endpoint. Design finite mastery arcs.

---

## System Design Principles

**Roguelike / Systemic approach** (recommended for small teams):
- Same systems generate endless novel experiences → best content ratio
- Favor **horizontal variance** (qualitative, incomparable outcomes) over vertical (power tiers)
- Horizontal drives curiosity; vertical produces power rushes but degrades into passive slot-machine

**Modularity rule**:
Synergies are a downstream effect of modularity, not a design goal.
Design components that can be separated and recombined.
Less interesting individual components → better system design.

**Every addition makes the game worse by default**:
New content must justify the noise it creates.

---

## Scoping for Mobile (Anti-Pattern List)

- **Anti-pattern**: RPG content ratio (hours of creation, seen once) → prefer systemic
- **Anti-pattern**: Three C's complexity (character/control/camera) → use vehicle, UI, or 2D top-down
- **Anti-pattern**: GDD as a crutch → design doc = one page with central illustration + annotations
- **Anti-pattern**: feature creep → every feature must serve a pillar
- **Anti-pattern**: "open world" scope → mobile session pattern contradicts open-world flow

**Miyamoto's filter**: a good mobile idea solves two problems simultaneously:
reduces developer workload AND improves player experience. If an idea only does one, keep looking.

---

## Time Limits & Pacing Mechanics

An underused but powerful design category — most mobile designers ignore it entirely.

### Timer Taxonomy (ascending player resistance)
1. **Bite-sized** — per-action timer (Chess clock, turn limit); low resistance
2. **Cycle timers** — day/season cycles (Stardew Valley, Majora's Mask 3-day loop, roguelite run clock); medium resistance
3. **Action-based game-wide** — calendar with a deadline (Persona's school year); high but acceptable
4. **Real-time game-wide** — actual wall clock counts down; highest resistance, rarest, most effective when done right

**Key insight** (from game_design_context.txt): players *fear* timers constantly but almost no games include them — creating a circular adoption trap. A well-designed timer is a meaningful differentiator.

### Disguise Constraints as Thematic Elements
FTL's rebel fleet is a hunger clock. A literal "30-second timer" would feel arbitrary;
a pursuing fleet is immersive. The constraint is identical; the theming makes it tolerable.

**Mobile applications**:
- Energy/lives system → framed as stamina, action points, or resources (not "you must wait")
- Daily mission timer → framed as "today's challenges", not a countdown
- Season end → framed as "don't miss the reward" rather than "your progress expires"

**The UNSIGHTED model**: make side content the primary source of time extensions,
so exploration IS survival. Dissolves the problem of a story urgency mechanic coexisting
with optional side quests — the side quests are how you don't die.

### Cycle Timers for Mobile Retention
Cycle timers (daily reset, weekly reset, seasonal reset) are the dominant mobile timer type:
- Daily reset: fresh daily objectives reset engagement trigger; most common
- Weekly guild war: scheduled conflict drives peak engagement sessions
- Season end: concentrated urgency in final week; drives conversion events

Design rule: **a mod that disabled FTL's rebel fleet proved its necessity — the game collapsed
without it**. If your timer can be removed without loss, it was decoration. If removal collapses
the session pattern, it was architecture.

---

## Replayability & Underused Mechanics

Design for replayability from the start, not as a retrofit.

### Tiered Risk/Reward (All Tiers Required)
Gears of War's Active Reload has three outcomes, but most copycats implement only two.
The "perfect reload = damage buff" tier creates genuine engagement.
Without the top tier, the mechanic is just "speed bonus + failure state" — shallow.

**Design rule**: if your mechanic has risk levels, all tiers must be implemented and visually communicated.
A two-tier system where tier 3 "is being worked on" = a broken mechanic in players' hands.

**Mobile applications**:
- Perfect-timing tap → critical hit / bonus reward (not just "normal + fail")
- Long-press charge → three power levels, not two
- Combo streak → degrading combos with clear visual tiers

### Structural Analogues (Cross-Genre Inspiration)
FTL's split-screen combat came from recognizing an isomorphism with Tetris multiplayer.

When designing replayability mechanics, search for structural analogues in unrelated games:
- What makes a completely different genre replayable?
- Can that structure be transplanted with a new skin?

### Deferral Queues
Separate exploration pacing from action pacing:
- Queue encounters/events for batch resolution later
- Players explore freely; action happens when they choose to resolve the queue
- Mobile application: "resolve your battle queue" as a session-opening ritual

### Pointless & Unrewarded Mechanics (Preserve Some)
Attaching mechanical rewards to expressive actions destroys them (from game_design_context.txt):
- RDR2's greet/antagonize became honor-farming the moment it was tied to a stat
- Player-chosen unrewarded engagement creates genuine attachment, not conditioned response

**Design rule for mobile**: in a reward-dense game, leave 1–2 mechanics with no reward.
Players who discover these feel ownership. They share them. Unrewarded mechanics are community-building.

**Mobile examples**:
- A dance emote that does nothing except look fun
- An environmental object that reacts to touch but gives no reward
- A non-essential NPC interaction that has flavor dialogue but no quest hook

---

## Design Output Artifact

```
DESIGN DOCUMENT (one page target)
─────────────────────────────────────
Game title:
Core verb (3 words):
Design pillars (2–3, player-experience statements):

CORE LOOP:
  Action:
  Feedback (< 100ms):
  Reward:
  Next action trigger:
  Loop duration target: ___ min

SESSION ARC:
  Cold start hook:
  Core loop repetitions per session: ___
  Exit hook (open loop):
  Sessions/day target: ___

PROGRESSION:
  Milestone arc (start → end):
  Mastery challenge examples (3):
  Memento / physical proof:

MONETIZATION:
  Model: F2P / Premium / Paymium / Ads
  Trigger moment: (when player is most willing to pay)
  First IAP price point: $___
  Ad placement: (player-initiated / between levels / none)

DILEMMA TYPE PRESENT: [ ] Scarcity  [ ] Trade-off  [ ] Prediction

SCOPE:
  Systems count: ___
  Content type: authored / systemic / hybrid
  Target build time: ___ weeks
  Scope filter: "Don't make GTA. Make the bowling game from GTA."
  This game is: [specific scope statement]

GATE: pillars defined / loop spec written / monetization integrated / scope bounded
─────────────────────────────────────
```
