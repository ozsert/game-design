# Phase 6: POLISH — Knowledge Reference

Elevate the validated experience. Polish what matters; cut what doesn't.

---

## Mismatched Polish Is Worse Than Low Polish

If one system is highly polished, unpolished systems look comparatively worse.
A game with consistently ugly assets that match the theme is more playable than one
mixing polished and placeholder art randomly.

**Polish audit first**:
- Identify the 20% of the game players spend 80% of their time in
- Polish that ruthlessly; keep everything else at a consistent baseline

If you have no desire to polish a part, that's a signal it **shouldn't be in the game**.

---

## Resolution and Art Scope (Mobile-Specific)

- Dropping resolution from 640×360 to 320×180 improved art quality:
  the smaller canvas forced better decisions. Mobile screens are dense;
  design for clarity at small size, not maximum detail.
- Vector art forces geometric simplicity — advantage for non-artists
  (tool constraints produce coherent style automatically)
- Kit-bashing approach: assemble original-looking characters from components
- Asset pack coherence: a pre-existing matching asset pack gives atmospheric
  coherence for free — but if you haven't modified the assets, it's not your game

---

## Feel & Feedback Layer

The feel layer is separate from the logic layer. Polish them separately:

**Input feel**:
- Response time < 100ms for tap-to-action
- Anticipation animation (slight compression before jump)
- Overshooting animation (slight overshoot on landing)
- Haptic feedback on key events (iOS Taptic Engine, Android vibration)

**Reward feel (Resolution principle)**:
- Audio + visual + progression signal together >> any single element
- Coin collect: sound effect + particle burst + counter increment = triple signal
- Level complete: animation + music sting + star reveal + progress bar fill

**Wrong physics can feel better**:
Sliding that violates physics (increases speed, full rotation) feels better than physically accurate.
Ship the wrong physics because the wrong physics is more fun.

---

## Visual Communication Checklist

- **Affordances**: interactive elements must look different from decorative ones
- **State communication**: disabled, active, selected, locked states must be visually distinct
- **Feedback on action**: every tap must produce visible change within 100ms
- **Description as interface**: what you emphasize = what players interact with
  (spend 3 seconds animating a door = players try the door)

Mobile additions:
- Touch feedback: visual ripple or highlight on tap even before action resolves
- Progress indicators on all async operations (loading, saving, syncing)
- Empty states: what does the screen look like with no content? Design it.

---

## Audio Polish

**Adaptive audio** creates feel without complexity:
- Use noise to modulate pitch/volume on repeating ambient sounds → never sounds looped
- Music layers: add layers as tension increases (silence → ambient → melody → full)
- Mobile: test with sound off (40%+ of mobile players play muted)

**Audio director principle**: making your own sounds is a meaningful differentiator.
Stock library sounds are recognizable. Custom sounds = branded experience.

**FMOD approach** (if using): composer owns all audio logic and implementation,
then specifies exactly what events/data the engine needs. Decouples audio from engine work.

Mobile audio rules:
- No audio during first-launch tutorial (many users play in silent environments)
- Audio permission: don't assume; respect device mute switch on iOS
- Sound effects can be compressed heavily on mobile (16kHz, mono for SFX)
- Music: loop-point matters; seamless loop is a polish requirement, not a nice-to-have

---

## Performance Polish (Mobile Non-Negotiable)

Polish = stable performance on low-end devices.

Mobile performance checklist:
- [ ] 60fps (or locked 30fps) on the lowest supported device
- [ ] No frame spikes during core loop interactions
- [ ] Memory under 1.5GB at all times during gameplay
- [ ] Load time between scenes < 1 second
- [ ] Object pooling implemented for frequently spawned objects
- [ ] Particles: capped particle counts; burst particles disabled on low-end
- [ ] Shaders: mobile-optimized shaders (avoid post-processing stack on low-end)
- [ ] Battery: no unnecessary background work; pause physics/AI when app is backgrounded

**Profiling tool**: Unity Profiler / Xcode Instruments / Android Profiler. Profile on device, not editor.

---

## Onboarding Polish

After core validation, polish the entry experience:

- Remove all text instructions; replace with contextual in-world prompts
- Highlight the single interactable element on screen during tutorial steps
- Remove all friction between download and first satisfying moment
- First IAP offer: after first win, not before
- Rating prompt: after 3+ sessions AND a win (not after a loss, never on first session)

---

## Content Scheduling Polish

When the game with good ingredients feels slow:
- Add a new mechanic introduction every 3–5 levels (not per level — too fast)
- Reveal locked content preview at natural pause points
- Reorder: put the most satisfying moment of each session earlier, not at the end

---

## Polish Output Artifact

```
POLISH AUDIT
─────────────────────────────────────
High-traffic area (80% of player time): ___
Polish priority list (by player exposure, not dev preference):

INPUT FEEL:
  Tap-to-action response: ___ ms (target < 100ms)
  Key animations present: anticipation / overshoot / squash-stretch
  Haptics on: [ ] key wins  [ ] losses  [ ] power moments

REWARD SIGNAL (triple check):
  Audio: [ ] present  [ ] custom  [ ] stock
  Visual: [ ] particle  [ ] animation  [ ] none
  Progression: [ ] visible  [ ] counter  [ ] none

VISUAL COMMUNICATION:
  Interactive vs decorative elements: visually distinct [ ] yes  [ ] no
  State indicators: disabled/active/locked clear [ ] yes  [ ] no

PERFORMANCE (on lowest target device):
  Frame rate: ___ fps
  Load time: ___ sec
  Memory peak: ___ MB

AUDIO (muted test):
  Core loop playable without sound: [ ] yes  [ ] no
  Muted state communicates enough via visuals: [ ] yes  [ ] no

MISMATCHED POLISH CHECK:
  All systems at consistent quality level: [ ] yes  [ ] no
  Elements with no polish desire (signal to cut): ___

GATE: consistent quality baseline / performance target met / feel layer complete
─────────────────────────────────────
```
