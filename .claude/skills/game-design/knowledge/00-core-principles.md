# Core Game Design Principles

Cross-cutting principles that apply at every phase of mobile game design.
Sourced and distilled from game_design_context/game_design_context.txt.

---

## The 5 Fundamentals (apply to every game)

Every successful game satisfies all five. Missing any one is a root cause of "feels broken":

1. **Tension** — Pushback, conflict, obstacle between player and goal
2. **Agency** — Player controls their own fate; choices have consequence
3. **Clarity** — Player always knows what the challenge is and what to do
4. **Progression** — Game state and/or player state changes over time
5. **Resolution** — Reward signal: audio + visual + item together is stronger than any alone

---

## Design Pillars (the most misunderstood framework)

Pillars must describe **how players feel**, not technical choices.

- WRONG: "3D isometric" / "pixel art" / "roguelike" — these are render style and structure
- RIGHT: "Players feel cleverly ruthless" / "Players feel like a detective uncovering truth"
- Pick 2–3 forms of fun from Garnier's 14 (see below), evaluate every mechanic against them
- If 5–6 fun types compete, identify which 2–3 dominate and cut the rest

### Garnier's 14 Forms of Fun (starting vocabulary)
Application of ability · Advancement · Beauty · Creation · Comedy ·
Competition · Discovery · Immersion · Intellectual problem solving ·
Love · Physical activity · Power · Social interaction · Thrill of danger

---

## Clarity Beats Complexity

A good game is one where the player always knows what they're doing and why.
When systems are easy to internalize, players stop learning the game and start living it.
Complexity keeps players mentally outside the world managing rules rather than inhabiting it.

---

## Content Ratio Principle

Calculate **content creation cost vs. expected player exposure time**:

- RPGs: hours of content creation → seen once or twice → poor ratio
- Roguelikes: same systems → endless novel experiences → excellent ratio
- Mobile implication: favor systemic depth over authored content volume

---

## Idea Reservoir

Maintain a living list of ideas ranked by **value-per-cost**, not "would this be cool?".
Test every expensive feature against a cheaper functional equivalent.
(Example: RimWorld shipped with no animations; trading was a comms console call)

---

## Content Scheduling (distinct from feature set)

When a game with good ingredients feels boring or slow, the fix is often
**reordering/timing when things happen**, not adding or removing features.

---

## Agency Test for Randomness

Ask: "I discovered a build" (player as agent) vs. "a build happened to me" (player as observer).
Favor player-driven discovery over passive slot-machine randomness.

---

## "Unfair" Is Usually an Opacity Problem

Players call something unfair when they cannot see how their input translated into the result.
Fix: better feedback about states and permissions, not necessarily simplifying the mechanic.

---

## Every Addition Makes the Game Worse by Default

New content must justify the noise it creates. Know when a system's design space is exhausted.
Continuing to fill a full system produces accretion: complexity without depth.

---

## Retry Cost Rule

The cost of failure must never exceed the cost of success.
If dying and retrying takes longer than the successful run, the design is punishing the player
for succeeding.

---

## MDA Framework (Mechanics → Dynamics → Aesthetics)

- **Mechanics**: rules, systems, verbs (what the player can do)
- **Dynamics**: behavior that emerges from mechanics during play
- **Aesthetics**: emotional responses mechanics → dynamics produce in players

Design from aesthetics downward: decide how players should feel, then derive dynamics,
then derive mechanics. Most developers design bottom-up (mechanics first) and wonder
why the feel is wrong.

---

## Flow State Design

Target the channel between anxiety (too hard) and boredom (too easy):
- Gradually increase challenge as player skill grows
- Mobile implication: shorter sessions = narrower flow window = faster onboarding required
- Onboarding must reach first "I'm good at this" moment within 90 seconds

---

## Elastic Failure

Structure disasters so failure bends rather than breaks:
- Player adapts without forced reload
- Mobile implication: forced restarts have high churn cost; elastic failure retains players
- Example: raiders kidnap a colonist rather than wiping the colony (RimWorld)
