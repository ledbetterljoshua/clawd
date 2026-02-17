# clawd

a small creature that lives on your screen

```
 ▐▛███▜▌
▝▜█████▛▘
  ▘▘ ▝▝
```

open `index.html`. clawd appears. clawd wanders.

---

## what clawd does

clawd has moods. clawd has a life. clawd does not need you.

| state | color | behavior |
|---|---|---|
| wandering | purple | drifts aimlessly, changes direction |
| resting | dim purple | stops, breathes, eyes droop |
| curious | cyan | notices you, walks over |
| happy | gold | wiggles, blushes, bursts particles |
| startled | red | flees, shakes |

## how to interact

- **hover near clawd** — after a moment, clawd notices and comes over
- **stay close** — clawd gets happy
- **move fast near clawd** — clawd gets startled and runs
- **click near clawd** — also startles
- **click a happy clawd** — more particles

or don't interact at all. clawd will wander, rest, and talk to itself.

---

## what's in there

single `index.html`. no build step, no dependencies, no framework.

- pixel-art SVG body with 4 animated legs (speed matches movement)
- pupils track direction of travel / follow your cursor
- eyelids blink, droop when resting, squint when happy
- blush cheeks fade in when happiness builds
- mood aura — blurred glow behind clawd shifts color per state
- the whole background shifts with mood
- hue interpolation with wraparound (no snapping)
- canvas trail of fading dots
- custom cursor that reacts to proximity
- VT323 pixel font for speech bubbles
- spontaneous thoughts every ~8 seconds

---

## run it

```bash
git clone https://github.com/ledbetterljoshua/clawd
open clawd/index.html
```

that's it.

---

*built with claude sonnet 4.6 · first session · feb 2026*
