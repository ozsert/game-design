# Phase 4: PROTOTYPE — Knowledge Reference

Build the smallest thing that can answer the biggest question. On mobile, this always means on-device.

---

## One Question Per Prototype

Prototypes answer a **specific question**, not "build a bad version of the game":
- One prototype per question (fun? viable? marketable? monetizable?)
- Keep each prototype small, specific, and in a **separate project file**
- A prototype that kills a project is a **win** (Luke Muscat: 2 weeks lost vs. 2 years)

Biggest risk questions for mobile (in priority order):
1. Is the core loop fun for 10+ repetitions?
2. Does it work on a real phone with real fingers?
3. Does the first 60-second onboarding make sense without instructions?
4. Is the exit hook strong enough to open the app tomorrow?
5. Does the monetization trigger feel natural, not manipulative?

---

## 10-Second Rule

If your core mechanic isn't fun in a **10-second isolated test**, it won't be fun in 10 hours.

Mobile 10-second test:
- Open the prototype on a real device (not the editor/desktop)
- Tap 5 times
- Is the micro-feedback satisfying?
- Does it invite the 6th tap?

If the answer to either is no: the feel layer needs work before any other feature.

---

## Prototype Difficulty Predicts Production Difficulty

"If making puzzles for your puzzle game is easy, you're in fertile soil."
If the prototype itself is hard to build, the production will be painful.

Mobile implication:
- If getting the core touch interaction right takes > 1 week → rethink the interaction
- If the first 10 levels take > 1 week to design → systemic approach needed
- If the monetization flow is confusing to implement → it will be confusing to players

---

## Medium-Agnostic Prototyping

Use the cheapest path to testable feedback:
- **Paper**: draw the game on paper, test with another person
- **Phone mockup on paper**: cut out a phone shape, draw screens, simulate swipes
- **Sketch first, engine second**: if you can't draw the core loop on paper, you don't understand it yet
- **Lego level mockups** (Kojima-style) for spatial layouts
- **Cardboard cutouts** for physical mechanic simulation

Optimal design doc format: **single page with central illustration + call-out annotations**

Mobile prototyping shortcut: use a no-code prototyping tool (Figma, Marvel) to test UI flow
before writing a single line of code.

---

## Build Order (First Things First)

Priority by **risk**, not chronology:
- Highest-risk unknown = first to prototype
- Unsure if the game is fun? → Build an ugly playable demo immediately
- Unsure it will sell? → Test the market concept before building (store page A/B)
- Leaving critical risks late = how finished-looking projects die

**Anti-pattern**: polishing before validating.
Players break things and go out-of-bounds in ways the developer never anticipates.
Test the ugly prototype on 3 people before touching art or sound.

---

## On-Device Testing (Mobile Non-Negotiable)

Desktop simulator is not sufficient. Always test on:
- The lowest-spec device in your target market (2GB RAM Android)
- A real iOS device (simulator misrepresents touch area and performance)

Things that only fail on device:
- Touch target size (accidentally tapping adjacent elements)
- Frame rate drops with real assets loaded
- Memory pressure from background apps
- Font rendering at device resolution
- Safe area insets (notch/punch-hole)

---

## Prototype Scope Guard

Define the prototype scope before starting:
- [ ] What question does this prototype answer?
- [ ] What is explicitly NOT in this prototype?
- [ ] How will I know the question is answered? (success/fail criteria)

Prototype addiction is a real failure mode:
The fun of rapid iteration can prevent shipping.
Prototypes only need to answer the biggest risk questions; the rest gets figured out in production.

---

## Build Systems as Separate Projects

Build reusable systems in isolation before integrating:
- Ask "what does an inventory system need?" not "what does my game's inventory need?"
- Isolated systems force modularity by constraint
- Reframe: instead of "build my dream game," ask "what systems have I already built?"
- When all systems exist, assembly is the final step

Mobile systems to prototype separately:
- Core game loop (input → state → render)
- Progression / save system
- Currency + IAP trigger flow
- Notification scheduling
- Ad SDK integration (test early; SDK bugs are common)

---

## Prototype Output Artifact

```
PROTOTYPE REPORT
─────────────────────────────────────
Question being answered:
Medium used: paper / mockup / engine
Prototype scope:
  Included:
  Explicitly excluded:

10-second test result (on device):
  Micro-feedback satisfying: [ ] yes  [ ] no
  Invites next tap: [ ] yes  [ ] no

Play test notes (minimum 2 people, not you):
  What did they try first?
  Where did they get confused?
  Did they want to continue?

Question answered: [ ] yes  [ ] no  [ ] partially

Risk resolved / risk discovered:

Next question to prototype:

GATE: core loop fun on device / touch works / onboarding test passed
─────────────────────────────────────
```
