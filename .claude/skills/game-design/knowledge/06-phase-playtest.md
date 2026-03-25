# Phase 5: PLAYTEST — Knowledge Reference

Validate the core loop with real players on real devices before polishing anything.

---

## Feedback Failure Mode (The Most Common Mistake)

Developers polish before validating.
Test the core loop on a basic prototype first.
Players break things and go out-of-bounds in ways the developer never anticipates.

**Polish before validation = wasted work**. The core loop must survive ugly first.

---

## Reading Playtest Signals

Player hesitation, random probing, and defaulting to wrong actions are diagnostic signals:

> "If reasonable people repeatedly make the same mistake, the system is teaching that mistake."

| Signal | Root Cause |
|--------|-----------|
| Players miss an obvious thing | Signifier failure (visual affordance broken) |
| Players never use a mechanic | Reward loop not communicating value |
| Players use violence/aggression as default | Reward loop mapping that to progress |
| Players ask "what do I do?" | Clarity failure (5 Fundamentals violation) |
| Players feel cheated after losing | Opacity problem, not balance problem |

**Fix opacity before nerfing difficulty.**

---

## The "Unfair" Diagnosis

Players call something unfair when they cannot see how their input translated into the result.
This is **almost never a balance problem** — it's a feedback problem.

Fix sequence:
1. Add more feedback about what happened and why
2. Check if the cause-effect chain is legible
3. Only adjust numbers if the chain is legible but the numbers are wrong

---

## Agency vs. Communication Failure

Two distinct problems that look identical:
- **Agency**: player knowingly subverts the intended encounter after understanding it → working
- **Communication failure**: player acts unexpectedly because they never had enough information → broken

Test by asking after each session: "Why did you do that?"
If they describe intent (agency), the design works. If they describe confusion (communication failure), fix the information.

---

## Difficulty Axes (Treat Separately)

Three distinct factors — never conflate them:
1. **Mechanical** (obstacle skill) — twitch, timing, precision
2. **Endurance** (back-to-back execution) — tests consistency, not peak skill
3. **Puzzle** (figuring out what to do) — knowledge and deduction

Mobile implications:
- Puzzle + high mechanical = frustration by design; keep separate
- Endurance + high mechanical = most replayable content
- Combining all three at high intensity → optional content only

---

## Knowledge as Design Material

Player knowledge state is a design material:
- **Ambiguity**: player doesn't know → creates exploration tension
- **Absence**: player knows nothing → creates frustration without payoff
- **Near-correctness**: player has almost-right model → hardest to escape; can be hostile

**Opaque mechanics are only justified if the mystery is worth solving.**
Withholding information about dull mechanics is hostile design that drives players to walkthrough videos (and then away).

---

## Onboarding (Mobile-Critical)

Mobile onboarding has 60–90 seconds before first-session dropout becomes likely.

Rules:
- **First win within 60 seconds**: player must feel competent immediately
- **Interactive tutorial only**: no text walls; show, then let player do
- **Pavlovian conditioning first**: reward curiosity before it's required
  (tapping non-essential elements → small animation/sound → conditions the behavior)
- **Tram sequence principle**: first path is linear; use it to teach game structure
- **Show locked content early**: desire is created by denial, not description
- **Never ask for permissions at launch**: request push notification after first win

**Puzzle mindset conditioning**: if your game is a puzzle game, teach players to be curious
before the first puzzle appears. Make decorative elements interactive and rewarding.

---

## Retry Cost (Mobile Retention Factor)

The cost of failure must never exceed the cost of success.

Mobile specifics:
- Long respawn sequences → high churn on first death
- Level restart from beginning after 10-min attempt → uninstall trigger
- Lives system: each life = short attempt; loss feels proportionate
- Elastic failure preferred: player adapts without forced restart

**Retry loop target**: < 10 seconds from fail to back in action (hyper-casual / casual)
< 30 seconds acceptable for mid-core

---

## Content Scheduling vs. Feature Set

When a game with good ingredients feels boring or slow, the fix is often:
**Reordering/timing when things happen**, not adding or removing features.

Playtest diagnosis:
- "This is boring" at minute 3 → something new needed at minute 2
- "This is too much at once" at minute 1 → spread reveals across first 5 minutes
- "I don't know what to do" at minute 5 → gate the next mechanic with a clear hook

---

## QoL and Convenience Features

QoL features should be **deliberately withheld until the player has earned context**:
- Fast travel / skip mechanics: introduce after player has learned to navigate manually
- Automation: introduce after player has mastered the manual version
- Too-early convenience = players never learn the system = players feel disengaged

Mobile specific: tutorial skip is fine; skip the explanation, not the learning.

---

## Playtesting Format for Mobile

**Session 1** (first-time player, cold start):
- Watch, don't help
- Note: first thing they tap, first confusion, first delight
- Target: 5+ minutes engagement without help

**Session 2+** (returning player, Day 2 simulation):
- What do they do within first 30 seconds?
- Did the exit hook work? Do they remember what they were doing?
- Are they progressing through the content curve or stuck?

**Remote playtesting tools**: TestFlight (iOS), Google Play Internal Testing (Android)
Minimum: 5 testers for meaningful signal; 20+ for statistical confidence.

---

## Playtest Output Artifact

```
PLAYTEST REPORT
─────────────────────────────────────
Build version / date:
Testers (count + profile):

FIRST SESSION OBSERVATIONS:
  Time to first "win" feeling: ___ sec
  First confusion point:
  First delight moment:
  Session length achieved: ___ min (target: ___ min)
  Completed session without help: [ ] yes  [ ] no

SIGNAL ANALYSIS:
  Clarity failures (what they did wrong repeatedly):
  Opacity problems ("unfair" moments):
  Exit hook strength: [ ] strong  [ ] weak  [ ] none

DIFFICULTY AXIS CHECK:
  Mechanical difficulty: appropriate / too high / too low
  Puzzle difficulty: appropriate / too high / too low
  Endurance appropriate: [ ] yes  [ ] no

RETENTION SIGNAL:
  "Would you open this tomorrow?": ___ / 5 testers said yes
  Verbal reason for yes/no:

CHANGES REQUIRED BEFORE POLISH:
  Critical (blocks core loop):
  Important (degrades experience):
  Minor (cosmetic):

GATE: core loop validated / retention signal positive / critical issues resolved
─────────────────────────────────────
```
