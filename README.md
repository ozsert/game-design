# game-design Skill

A mobile game design consultant skill for Claude Code, covering the full lifecycle
from concept to postmortem. Focused on iOS and Android.

---

## How to Use

Type `/game-design` in any Claude Code session inside this project.

You can:
- **Start a new game**: describe your idea and the skill guides you phase by phase
- **Jump to a phase**: "I'm in DESIGN phase, help me with the core loop"
- **Ask a specific question**: "What's the right monetization model for a puzzle game?"
- **Request a review**: the skill reads your existing design document and audits it

## The Living Design Document

Every game produces one design document in the project root: `{GAME_TITLE}_DESIGN.md`.

- Phases append to the file as they complete
- Completed phases are marked `✓`; the current phase shows `in progress`
- The document is the source of truth — the skill reads it before every response
- At Phase 8 completion, it is the full historical record of the game

---

## File Structure

```
{project root}/
├── README.md                       ← this file
├── .gitignore
└── .claude/skills/game-design/
    ├── SKILL.md                    ← entry point; phase router; cross-phase rules
    └── knowledge/
    ├── 00-core-principles.md       ← always-active game design theory
    ├── 01-mobile-design-context.md ← always-active mobile platform context
    ├── 02-phase-conceive.md        ← Phase 1
    ├── 03-phase-validate.md        ← Phase 2
    ├── 04-phase-design.md          ← Phase 3
    ├── 05-phase-prototype.md       ← Phase 4
    ├── 06-phase-playtest.md        ← Phase 5
    ├── 07-phase-polish.md          ← Phase 6
    ├── 08-phase-launch.md          ← Phase 7
    ├── 09-phase-postmortem.md      ← Phase 8
    ├── 10-genre-patterns.md        ← loaded when genre is known
    └── 11-live-service.md          ← loaded when F2P / live service applies
```

---

## Knowledge Architecture

The knowledge is split into three layers. Each layer answers a different question.

### Layer 0 — Always Active (00, 01)

These two files are loaded at the start of every session and remain active throughout.
They answer: **"What are the constants?"**

**`00-core-principles.md`** — Pure game design theory.
Principles that are true regardless of platform, genre, or phase:
- The 5 Fundamentals (Tension, Agency, Clarity, Progression, Resolution)
- MDA framework (design from aesthetics down, not mechanics up)
- Design pillar methodology (pillars describe feeling, not technology)
- Content ratio principle (systemic vs authored)
- Elastic failure, retry cost rule, agency vs randomness

This file sources primarily from `game_design_context/game_design_context.txt` —
distilled expert knowledge from 100+ game design videos. It contains no mobile-specific
content; these are universal design truths.

**`01-mobile-design-context.md`** — Mobile platform design constraints.
Facts about iOS and Android that shape every design decision:
- Session length targets by genre (hyper-casual 2–4 min → mid-core 15–25 min)
- Monetization models and when each fits (F2P / Premium / Paymium / Ads)
- Retention benchmarks (D1/D7/D30 targets by genre)
- Key KPIs a designer must understand (LTV, CPI, ROAS, Stickiness)
- Mobile genre landscape (what exists, what monetizes how)
- Touch design principles (thumb zone, portrait one-thumb rule)
- ASO design implications (icon signals the loop; video shows the verb)

This file contains no game design theory and no technical implementation specs.
It is the market and platform reality layer — what is true about mobile as a medium.

> **Why separate 00 and 01?**
> Game design theory (00) and mobile platform context (01) change at different rates
> and for different reasons. Theory evolves over years through research and craft.
> Platform context evolves over months through market shifts and store policy changes.
> Keeping them separate makes each easier to update independently.

---

### Layer 1 — Phase Knowledge (02–09)

One file per phase of the design lifecycle. Each file is loaded only when its phase is active.
They answer: **"What do I need to know and do right now?"**

Each phase file contains:
- **Frameworks**: the models and mental tools for this phase
- **Questions**: what to ask before advancing
- **Mobile filters**: phase-specific mobile constraints
- **Output artifact**: a concrete template to fill out before moving on
- **Gate**: the explicit go/no-go criteria to advance to the next phase

| File | Phase | Core Question |
|------|-------|--------------|
| `02-phase-conceive.md` | CONCEIVE | Is this concept worth pursuing? |
| `03-phase-validate.md` | VALIDATE | Does market reality support this concept? |
| `04-phase-design.md` | DESIGN | What exactly are we building and how? |
| `05-phase-prototype.md` | PROTOTYPE | Does the core loop work on a real device? |
| `06-phase-playtest.md` | PLAYTEST | Do real players engage with this? |
| `07-phase-polish.md` | POLISH | Is every part at a consistent quality level? |
| `08-phase-launch.md` | LAUNCH | Is the game ready for the global market? |
| `09-phase-postmortem.md` | POSTMORTEM | What did we learn and what comes next? |

The phase numbering (02–09) is intentional: files sort in the order they are used.
The 00/01 prefix keeps always-active files at the top.

> **Why not put all knowledge in SKILL.md?**
> Loading all knowledge at once for every question is wasteful and produces unfocused answers.
> A question about monetization in the CONCEIVE phase needs different knowledge than
> a question about monetization in the POSTMORTEM phase. Phase files keep context tight.

---

### Layer 2 — Conditional Knowledge (10+)

Loaded only when the game matches a specific category. They answer: **"What are the patterns for this type of game?"**

**`10-genre-patterns.md`** — Design patterns for the 6 dominant mobile genres:
Match-3 · Idle/Incremental · Endless Runner · Casual Puzzle · Roguelite · 4X Strategy.
Each genre section covers: core loop structure, retention mechanics, monetization fit,
and the most common failure modes. Loaded when the concept has a known genre.

**`11-live-service.md`** — Post-launch design for games with ongoing content.
Season calendar design, battle pass architecture, update cadence, community design,
power creep management. Loaded when the game uses F2P or has a live service model.

> **Why separate from phase files?**
> Genre patterns and live service design cut across multiple phases (DESIGN, PLAYTEST,
> LAUNCH, POSTMORTEM all need genre context). A cross-cutting concern that isn't specific
> to one phase belongs in a conditional file loaded when relevant, not repeated across phases.

---

## Knowledge Sources

| Layer | Primary Source | Secondary Source |
|-------|---------------|-----------------|
| `00-core-principles.md` | Distilled from 100+ game design videos (Pete Baron, MIT License) | Game design academic frameworks (MDA, flow state) |
| `01-mobile-design-context.md` | Industry benchmarks and platform knowledge | — |
| Phase files (02–09) | Distilled from 100+ game design videos | Mobile-specific extensions |
| `10-genre-patterns.md` | Mobile market knowledge | — |
| `11-live-service.md` | Live ops industry knowledge | — |

Original knowledge source: [game_design_context](https://github.com/pjbaron/game_design_context) by Pete Baron (MIT License, March 2026).
The skill extracts the ~50% of that document that is mobile-relevant and discards the rest (tabletop, wargame, VR, Steam/PC-specific sections).

---

## The 8 Phases

```
CONCEIVE → VALIDATE → DESIGN → PROTOTYPE → PLAYTEST → POLISH → LAUNCH → POSTMORTEM
```

Each phase has a **gate** — an explicit condition that must be true before advancing.
Gates prevent the most common failure modes (building before validating, polishing before
the core loop works, launching without soft launch data).

Phase gates are listed in `SKILL.md` and detailed in each phase file's output artifact section.
