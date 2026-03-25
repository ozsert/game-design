# Mobile Design Context (iOS & Android)

Design-layer constraints and market context for mobile game design decisions.
Technical implementation details (engine, RAM budgets, platform submission) are in
`build/mobile-build-constraints.md`.

---

## Session Design

Design every loop duration target around real player behavior:

| Genre | Avg Session | Core Loop Target | Orientation |
|-------|------------|------------------|-------------|
| Hyper-casual | 2–4 min | < 60 seconds | Portrait |
| Casual (puzzle/idle) | 5–10 min | < 3 minutes | Portrait |
| Hybrid-casual | 8–15 min | < 5 minutes | Portrait or Landscape |
| Mid-core (RPG/strategy) | 15–25 min | < 10 minutes | Landscape |
| Hard-core | 30+ min | varies | Landscape |

**Rule**: If a player can't understand your core loop in a single session, you lose them forever.
There are no "tomorrow I'll understand it better" players on mobile.

**Interruption design** (non-negotiable for all mobile):
- Game must be pause-safe at any moment
- Returning player must be able to orient in < 10 seconds
- Progress must auto-save; never lose session state

---

## Touch Design Principles (Design Constraints)

These are design decisions, not implementation specs:

- **Thumb zone**: primary interactions must live in bottom 60% of screen
- **Portrait one-thumb rule**: casual core loop must be completable with one thumb
- **No hover states**: all affordances must be visible at rest, not on hover
- **Swipe vs tap**: swipe = navigation/dismissal; tap = activation
- **Accidental spend prevention**: any action spending premium currency requires confirmation
- **Landscape**: requires two-hand engagement; acceptable for mid-core; increases engagement depth but reduces casual audience

---

## Mobile Monetization Models

Choose the model during DESIGN, not after:

### Free-to-Play (F2P) — Most common
- Premium currency + gacha / lootboxes / power packs + energy/lives system
- Best for: social, competitive, live service games
- **Whale economics**: 2–5% of players generate 50–80% revenue
- ARPU: $0.05–$0.30 casual | $1–$5 mid-core
- Design requirement: must have collectible or power identity to drive spending

### Premium
- One-time purchase: $0.99–$9.99
- Best for: narrative games, puzzle games, PC ports
- Design requirement: hook must justify the paywall decision at download

### Paymium
- Premium purchase + optional IAP
- Best for: sandbox, deep systems games (Minecraft model)
- Design requirement: IAP must feel like expansion, not unlocking locked content

### Ad-Supported Hybrid
- Rewarded video: player-initiated; highest CPM; treat as a design mechanic
- Interstitial: between natural break points only; never mid-action
- Banner: avoid; always interferes with core loop
- **Rewarded ads as design**: "Watch ad → extra life / currency / double reward"
  is a legitimate mechanic when optional and player-initiated

---

## Retention Benchmarks (Design Targets)

Design the core loop, progression, and exit hook to hit these:

| Metric | Hyper-casual | Casual | Mid-core | What It Measures |
|--------|-------------|--------|----------|-----------------|
| Day 1 (D1) | 35–40% | 40–45% | 35–40% | Core loop + onboarding |
| Day 7 (D7) | 12–15% | 20–25% | 15–20% | Progression hook |
| Day 30 (D30) | 4–6% | 8–12% | 8–12% | Mid-game depth |

**If D1 < 25%**: core loop or onboarding is broken. Stop all other work and fix this first.
**D7 gap**: if D1 is good but D7 drops sharply → exit hook is weak (no reason to return)
**D30 gap**: if D7 is good but D30 drops → mid-game content gap or infinite progression without satisfaction

---

## Key Mobile KPIs (Know Before Designing)

Design decisions must be compatible with the economics:

- **LTV** (Lifetime Value): the ceiling on how much you can spend per install. Design determines LTV.
- **CPI** (Cost Per Install): $0.50–$3 casual | $5–$20 mid-core | $20–$50 hard-core
- **ROAS** (Return on Ad Spend): target 100%+ at D30 for profitable UA
- **ARPDAU**: tracks how much each daily active user generates. Monetization design drives this.
- **Stickiness**: DAU/MAU ratio; 20%+ strong for casual. Session design drives this.

**Design implication**: if your genre's average CPI exceeds your monetization model's LTV →
the game is structurally unprofitable regardless of quality. Validate this in Phase 2.

---

## Mobile Genre Landscape (2024)

| Genre | Monetization | Dev Complexity | Leading Examples |
|-------|-------------|----------------|-----------------|
| Hyper-casual | Ads | Very low | Stack Ball, Helix Jump |
| Hybrid-casual | Ads + IAP | Low–medium | Royal Match, Merge Mansion |
| Match-3 | F2P | Medium | Candy Crush, Toon Blast |
| Idle / Clicker | F2P | Low | Adventure Capitalist |
| Merge | F2P | Low–medium | Merge Dragons |
| Runner | Ads / IAP | Low | Subway Surfers |
| Tower Defense | F2P / Premium | Medium | Kingdom Rush |
| Card / Deck-builder | F2P | High | Clash Royale |
| 4X Strategy | F2P | High | Rise of Kingdoms |
| Puzzle-narrative | Premium / F2P | Medium | Monument Valley |
| Roguelite | Premium / F2P | High | Slay the Spire (port) |

See `10-genre-patterns.md` for detailed design patterns per genre.

---

## Offline vs Online Design

Make this a design decision in Phase 3, not an afterthought:

- **Casual puzzle / hyper-casual**: offline-first; no internet required for core loop
- **Social / competitive / live service**: online required; design graceful offline degradation
- **Cloud save**: always implement; players switch devices; losing progress = immediate uninstall
- **Leaderboards**: design whether async (daily snapshot) or real-time; async is lower infrastructure

---

## Push Notification Design (Exit Hook System)

Notifications are a **design mechanic** — they extend the exit hook beyond the session:

- **D1 return**: "Your daily reward is waiting" (reward for returning)
- **D3 lapsed**: reference a specific open loop ("You were 3 moves away from completing level 7")
- **D7 lapsed**: social proof or FOMO ("10,000 players progressed while you were away")

Design constraints:
- Request permission **after the first win**, never at first launch
- Never send during a session
- Max 1 notification per day; more = uninstall
- Each notification needs a specific reason to open, not a generic "come back"

---

## ASO Design Principles (Affects Validate + Design)

These are design decisions, not marketing choices:

- **Icon must signal the core loop**, not just the genre
  (lone character = exploration; candy/gems = casual match; clock = time pressure)
- **Video preview first 3 seconds** must show the satisfying micro-loop
- **Game title** should contain what the player does ("Merge Town" not "City Dream")
- Design implication: if you can't show the core loop in 3 seconds of video,
  the loop isn't visual enough or isn't satisfying enough yet

---

## Soft Launch as Design Validation

Soft launch is the final design validation gate, not a marketing exercise:

- Markets: Canada · Australia · New Zealand · Nordics (similar to US/EU; lower CPIs)
- Gate: D1 ≥ 35% before global launch
- What to fix in soft launch: D1 (onboarding + core loop) first, then D7 (exit hook + progression)
- Duration: 2–4 months; do not rush to global if D1 is below gate
