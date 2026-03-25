# Mobile Genre Design Patterns

Design patterns, core loop structures, monetization fit, and failure modes
for the top mobile game genres. Load this file when the concept has a genre target.

---

## Match-3 / Tile-Swap

**Core loop**: swap adjacent tiles to make matches → chain reaction → clear board condition → star rating → next level.
**Meta loop**: level progression + home/build meta (spend earned currency to decorate/build).

### Design Patterns
- **Board state teaching**: early levels have one dominant match; complexity grows by adding new tile types one at a time
- **Near-miss engineering**: boards are seeded to create 1–2 near-completion moments; players see "almost" before they see "fail"
- **Booster placement timing**: introduce boosters after the first hard wall (typically level 10–15); withheld tools feel like earned power, not tutorials
- **Meta build as memento**: the home/build meta is the memento layer (see 00-core-principles.md); what you build is proof of your progress
- **Hard wall pacing**: difficulty spikes at levels 20, 50, 100 are intentional checkpoints, not bugs; they gate monetization

### Monetization Fit
- Lives system: 5 lives, refill over time → monetize continues at the wall
- Extra moves IAP: offered only after fail state ("Need 5 more moves?")
- Booster bundles: starter pack in first 2 days; highest conversion moment
- Battle pass: works well if update cadence supports it (weekly new levels)

### Common Failure Modes
- **Board complexity overload**: adding new tile types without removing old ones → confusion
- **Lives without retention**: energy system only monetizes if D7 is strong; weak D7 = no players to hit the wall
- **No meta progression**: pure level-runner with no build/collect meta → poor D30
- **Random unfair boards**: players must be able to see a path to winning even on hard levels

### Mobile-Specific
- Portrait only; one-thumb playable
- Session = 1–5 levels; natural stop point is level clear
- Sound design is critical: each match type needs a distinct audio cue

---

## Idle / Incremental / Clicker

**Core loop**: tap or wait → currency accumulates → spend on multipliers → numbers get bigger → prestige/reset for permanent bonus.
**Session pattern**: open app → collect offline production → spend → start new timers → close.

### Design Patterns
- **Offline production is the core retention mechanic**: the login reveal (seeing what accumulated) is a designed emotional payoff
- **Prestige loop**: resetting all progress for a permanent multiplier is the mid-game mastery arc; without it, progression stalls
- **Exponential numbers** need readability: abbreviate (1K, 1M, 1B, 1T) and use milestones (unlock new area at 1M)
- **Content unlock as chapter structure**: divide the infinite progression into chapters (Bakery → Restaurant → Hotel) to create visible arc
- **Idle speed cap**: production while offline should be capped (e.g., 4 hours max) to create daily check-in incentive

### Monetization Fit
- No ads during active play (players are in the "review production" flow)
- Rewarded ads: "Watch ad to 2× offline production for 2 hours" — extremely high conversion
- Time-skip IAP: skip ahead 8 hours; high value, low friction
- Permanent multiplier packs: best mid-game IAP for committed players

### Common Failure Modes
- **Number growth without meaning**: bigger numbers with no new content = player has no reason to continue
- **No prestige loop**: players reach a ceiling with no reset mechanic → terminal boredom at mid-game
- **Offline production too long**: if offline cap is 24 hours, no daily check-in incentive
- **No active play layer**: pure passive idle has lower retention than hybrid (active tap phase + idle phase)

### Mobile-Specific
- Portrait; minimal interaction design
- Session = 30 seconds to 3 minutes (check-in pattern)
- Cold start must show production immediately (numbers changing on screen)

---

## Endless Runner

**Core loop**: auto-move forward → dodge obstacles / collect items → die → revive / retry → score chase.
**Meta loop**: currency from runs → unlock characters / costumes → score multipliers.

### Design Patterns
- **Procedural difficulty**: obstacle density increases over time; player always dies to something new
- **Run arc**: early run = learning phase (0–30 sec); mid run = flow state (30 sec–2 min); late run = pure skill test (2 min+)
- **Daily challenge**: fixed seed run with leaderboard; drives social comparison and daily return
- **Character collection as memento**: unlocking characters via currency is the mid-game hook; cosmetics don't affect run but signal status
- **Death framing**: "You scored 2,450 — your best is 3,100" keeps attention on the gap, not the failure

### Monetization Fit
- Second-chance / continue: "Watch ad to revive" — high conversion in late run (player invested in the run)
- Coin doubler: permanent IAP; early purchase for committed players
- Character / cosmetic IAP: mid-game driver
- Ads between short runs: acceptable for hyper-casual; intrusive for mid-core

### Common Failure Modes
- **Obstacle spam**: difficulty by adding more obstacles = skill isn't the factor, RNG is → frustration
- **No run arc**: same difficulty from second 0 = no sense of "I'm getting further"
- **Cosmetics with no display**: collected costumes mean nothing if no one sees them; leaderboard avatars or menu display required
- **Slow death animation**: runner dies + 3-second animation + retry button = kills retry speed

### Mobile-Specific
- Portrait; one-thumb / swipe control
- Session = 2–5 minutes (multiple short runs)
- Sound design: rhythm and forward momentum critical to feel

---

## Casual Puzzle (Narrative Frame)

**Core loop**: solve spatial / logic puzzle → advance narrative chapter → unlock next puzzle set.
**Distinguishing design**: unlike match-3, these are authored puzzles, not procedural; each has one intended solution.

### Design Patterns
- **Puzzle as story beat**: each puzzle should represent a narrative moment, not just a difficulty gate
- **Solution elegance**: best puzzles have solutions that feel "of course" in retrospect; test with non-designers
- **Progressive mechanic introduction**: add exactly one new mechanic per chapter; never two at once
- **No dead ends**: player must always have moves available; "unsolvable state" is instant uninstall on mobile
- **Hint system**: provide 3 hints per puzzle; third hint should essentially solve it; respect the player's time
- **Difficulty arc**: hard puzzle → 1–2 easier puzzles as palate cleanser → next hard puzzle; rhythm, not escalation

### Monetization Fit
- Premium ($2.99–$4.99): works well if brand is established or art is exceptional
- F2P with hint IAP: hints as IAP or ad-rewarded; low friction
- Chapter unlock IAP: sell chapter packs; players pay for content, not to bypass difficulty

### Common Failure Modes
- **Puzzle requires knowledge outside the game**: solutions depending on trivia or real-world knowledge → hostile
- **Too many mechanics at once**: introducing 3 elements in one puzzle → cognitive overload
- **Mismatched difficulty curve**: easy start → sudden hard wall without gentle ramp
- **Narrative irrelevance**: story disconnected from puzzle mechanics → narrative feels like wallpaper
- **No undo**: player makes one wrong move and must restart entire puzzle → high churn

### Mobile-Specific
- Portrait preferred
- Session = 1–3 puzzles (natural stop point is chapter end)
- Accessibility: must work for color-blind players; never use color as the only differentiator

---

## Roguelite (Mobile)

**Core loop**: start run → choose upgrades → fight enemies → die → unlock permanent upgrade → stronger next run → clear boss.
**Key distinction from PC roguelikes**: mobile runs should complete in 15–30 minutes max; PC roguelikes can be 1–3 hours.

### Design Patterns
- **Horizontal variance over vertical** (see 00-core-principles.md): build choices that are qualitatively different, not just quantitatively stronger
- **Permanent progression as engagement bridge**: players who died 10 times must feel net progress; meta currency for permanent unlocks provides this
- **Run length calibration**: each run should fit in one mobile session; if a run takes 45+ minutes, add mid-run save or cut content
- **Synergy discovery as the loop**: the moment a player realizes two items combine unexpectedly is the retention hook; design for these moments
- **Starting builds**: offer 3+ starting loadouts after first run; choice of identity is the first retention signal
- **Mobile enemy complexity**: on mobile, telegraphing must be faster and clearer than PC; visual warnings must be readable at glance

### Monetization Fit
- Premium ($4.99–$7.99): highest fit for PC-port roguelites with established audiences
- F2P with cosmetics: run-neutral cosmetics (character skins, effect skins) preserve game integrity
- Avoid: power-for-pay in roguelites; community perception damage is severe and permanent
- Battle pass: works if cosmetics are differentiated and season adds new starting options

### Common Failure Modes
- **Runs too long for mobile**: a 45-minute run with no save = players never finish; see content cut guidelines
- **Meta progression too slow**: if it takes 20 failed runs to feel stronger, D7 is doomed
- **No horizontal variance**: every run feels like the same power path → loop is shallow
- **Synergy opacity**: players don't know items interact → random feeling, not discovery feeling
- **Port complexity without touch redesign**: PC-style multi-button combat ported directly to mobile fails; redesign for 2–3 input actions maximum

### Mobile-Specific
- Landscape preferred for complex combat; portrait works for turn-based
- Session = one complete run or a mid-run checkpoint
- Touch: reduce to 3 actions maximum (attack / special / dodge); PC port often requires full rethink

---

## 4X / Grand Strategy (Mid-Core)

**Core loop**: build base → train units → attack enemy → gain resources → expand → larger attack.
**Meta loop**: season/league ranking + alliance competition + long-term base development.

### Design Patterns
- **Speed-up economy is the core design**: player time is the primary resource; speed-ups collapse time; premium currency buys speed-ups
- **Construction queue as retention mechanic**: queued buildings = reason to check back in 2 hours
- **Alliance social contract**: players who join alliances have 3× retention; solo players churn at mid-game; design alliance incentives early
- **March mechanic**: troops in motion = visual feedback and anticipation = session engagement hook
- **Alliance war as live event**: scheduled conflict with known start/end time drives session peaks
- **Catch-up mechanics**: new players in a 6-month-old server die immediately without protection shields and starter boosts

### Monetization Fit
- The dominant model: whale-driven F2P; top 1% spend > $1,000/month
- Speed-up bundles: highest volume IAP
- VIP system: subscription-like tier with permanent conveniences
- Builder's second queue: classic mid-game gating mechanism; hard to resist for committed players

### Common Failure Modes
- **Server age gap**: new players on old servers have no path to relevance → churn; design realm/server merging
- **Solo playability collapse**: if the game becomes unplayable without alliance participation at week 2 → large casual audience lost
- **Combat opacity**: if attack outcomes depend on invisible stats, results feel random → frustration
- **No comeback mechanic**: a player who goes offline for 3 days returns to a burned base with no path forward → permanent churn
- **Update content for whales only**: new content that only top-tier spenders access kills mid-tier player investment

### Mobile-Specific
- Landscape mandatory; complex UI requires two-hand interaction
- Session = 5–15 minutes (check-in + action queue refresh)
- Always-online required; design graceful offline state (resource accumulation continues; cannot be attacked while offline up to a shield limit)
