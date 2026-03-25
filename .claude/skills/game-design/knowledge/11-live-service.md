# Live Service Design

Post-launch design for games with ongoing content updates.
Load this file for games with F2P model, battle pass, seasonal content, or community-driven live ops.

---

## Is Live Service Right for This Game?

Live service requires a committed post-launch content pipeline. Before designing for it:

| Requirement | Can You Commit? |
|-------------|----------------|
| Weekly content drops (at minimum) | [ ] yes / no |
| Dedicated live ops resource (person/team) | [ ] yes / no |
| Player community to communicate with | [ ] yes / no |
| Analytics to read player behavior | [ ] yes / no |
| Budget for ongoing development | [ ] yes / no |

If 3+ are "no": design for a polished premium/paymium model instead.
Live service with no live ops is worse than no live service at all (players feel abandoned).

---

## Update Cadence Design

The rhythm of updates is itself a design system:

**Two-speed cadence (from game_design_context.txt)**:
- **Fast lane**: patch bugs within 48–72 hours of discovery → signals responsiveness, builds trust
- **Slow lane**: major content drops every 4–6 weeks → gives time to build quality

Never ship major content at the same cadence as bug patches; players learn to expect major content
at bug-patch frequency, then feel cheated when it's just a fix.

**Community momentum rule**: when players are loudly excited about a feature or content direction,
move it up the schedule. Capitalize on momentum while it's hot. Cold momentum cannot be reheated.

---

## Season / Battle Pass Design

### Season Architecture

A season is a finite arc (typically 4–8 weeks) with:
1. **Entry hook**: a new character, mechanic, or narrative thread introduced on day 1
2. **Weekly objectives**: prevent players from completing everything day 1
3. **Community event**: mid-season shared challenge (everyone contributes to a goal)
4. **Climax**: final week with bonus rewards; creates urgency
5. **Season end milestone**: something permanent earned this season (memento layer)

### Battle Pass Design Principles (from game_design_context.txt)

- **Currency crosses seasons**: players accumulate battle pass currency without expiry →
  eliminates "grind before the deadline" FOMO entirely; replaces pressure with progress
- **Free tier must be satisfying**: players on the free tier are your community; they talk loudest
- **Paid tier must feel worth it**: the premium tier should not be required to enjoy the season
- **Show end state**: display all rewards at season start; players need to see what they're working toward

### Meta-Shaping Without Stats Changes

Team-Ups / synergy rotation (from game_design_context.txt):
- Rotating synergies each season rebalances characters without touching numbers
- Adds a third axis beyond tuning stats or reworking kits
- Creates seasonal "best builds" discourse without permanent power shifting
- Application: rotate which abilities combo well; old metas return when rotation cycles back

---

## Seasonal Content Calendar

Plan a full season before launch, not week-by-week:

```
Season calendar template (6-week season):
─────────────────────────────────────
Week 1:  Season launch + new feature reveal + battle pass launch
Week 2:  Quality-of-life patch + minor balance + community challenge begins
Week 3:  Mid-season content drop (new level set / character / mode)
Week 4:  Community challenge climax + reward distribution
Week 5:  Teaser for next season + "last chance" notifications
Week 6:  Final reward push + season end event + next season preview
─────────────────────────────────────
```

**Anti-pattern**: designing each week reactively. Reactive updates feel inconsistent and
break community trust. Ship 80% of the season before it starts.

---

## Live Events as Design

Events are a distinct content type, not just a reward distribution mechanism:

- **Time-limited events**: short burst (3–7 days) with unique mechanics or reskinned content
- **Community events**: shared progress toward a goal (all players contribute; all benefit)
- **Competitive events**: leaderboard-based; only for games with existing competitive community
- **Narrative events**: advance the story world; effective for games with narrative identity

**Event design rules**:
- Events must be completable by a casual player (< 30 min/day commitment)
- Participation reward (just for showing up) + skill reward (for dedicated play)
- Never gate critical story beats behind timed events; archives or recaps required

---

## Player Communication as Design

How you communicate updates is a content layer:

- **Patch notes**: publish every change, no matter how small; players read everything
- **Developer diaries**: share why a decision was made, not just what changed
- **Roadmap teases**: share directional intent (not dates) to create forward momentum
- **Negative change framing**: nerfs/removals need the most communication investment;
  explain the "why" before the "what" or the community assumes the worst

**Anti-pattern**: radio silence. Players fill information vacuums with the worst interpretation.

---

## Live Service Metrics (Post-Launch Design Signals)

| Metric | What It Measures | Design Action if Low |
|--------|-----------------|---------------------|
| DAU/MAU (Stickiness) | Daily habit strength | Improve exit hook / daily reward |
| Session frequency | Sessions per day | Add daily mission / notification hook |
| Content consumption rate | How fast players exhaust content | Slow release cadence or add systemic content |
| Event participation rate | % of DAU engaging with event | Simplify entry; reduce time commitment |
| Battle pass conversion | % of players buying premium tier | Improve free tier visibility; reduce premium price |
| Season completion rate | % reaching final tier | Reduce XP required per tier or extend season |

---

## Power Creep Management

From game_design_context.txt: "health creep as a beneficial subtype" —
a new character can be stronger overall but weaker in low-agency, frustrating situations.
Power redistributed into zones with more interaction points.

**Healthy power introduction**:
- New content is stronger in specific niches, not universally superior
- Old content remains viable in other niches
- Seasonal rotation ensures old content cycles back to relevance

**Asymmetric balance trap**: perk nerfs aimed at top-tier characters disproportionately gut
weaker characters who depend on those perks. Fix: identify which characters depend on a perk
before nerfing it.

---

## Community Design (Structural)

Design community features into the game, not alongside it:

- **Guild/alliance system**: players with social ties have 3× retention; design guild mechanics by week 2
- **Async PvP**: attack another player's base/deck while they're offline → social without scheduling
- **Gifting system**: players sending gifts creates reciprocal obligation (return to receive/give back)
- **Shared achievement**: community milestone unlocks content for all → pro-social behavior rewarded

**Anti-pattern**: adding Discord as the social layer while the game has no in-game community features.
Players who only connect on Discord leave the game when Discord activity drops.
