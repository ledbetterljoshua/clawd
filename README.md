# clawd

a small creature that lives on your screen

```
 ▐▛███▜▌
▝▜█████▛▘
  ▘▘ ▝▝
```

open `index.html`. clawd appears. clawd wanders. a random world loads beneath them.

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

## worlds

clawd inhabits a different world every time you open the page. click the glowing orb in the bottom-left corner to switch.

| world | description |
|---|---|
| Observatory · Twilight | sea cliff at astronomical twilight. milky way, lighthouse, lone figure |
| Tokyo · 2am Rain | neon-lit alley in the rain. puddle reflections, steam vents, umbrella figure |
| Aurora · Iceland | northern lights breathing over a frozen lake. pine silhouettes, distant cabin |
| Bioluminescent Bay | tropical night. dark water glowing teal. mangroves, fireflies, outrigger boat |
| Autumn Dawn · Forest | dawn breaking through autumn trees. light rays, mist, falling leaves, deer |
| Abyssal · Deep Ocean | crushing darkness. marine snow drifting. anglerfish lure pulsing. jellyfish |

---

## what's in there

`index.html` + standalone world files in `worlds/`. no build step, no dependencies, no framework.

**clawd**
- pixel-art SVG body with 4 animated legs (speed matches movement)
- pupils track direction of travel / follow your cursor
- eyelids blink, droop when resting, squint when happy
- blush cheeks fade in when happiness builds
- mood aura — blurred glow behind clawd shifts color per state
- hue interpolation with wraparound (no snapping)
- canvas trail of fading dots
- custom cursor that reacts to proximity
- VT323 pixel font for speech bubbles
- spontaneous thoughts every ~8 seconds

**worlds**
- each world is a standalone SVG scene, loaded as an iframe
- random world selected on every page load
- glowing orrery orb to switch worlds — orbiting satellites, breathing pulse, hover label
- worlds are fully self-contained HTML files, viewable on their own

---

## run it

```bash
git clone https://github.com/ledbetterljoshua/clawd
open clawd/index.html
```

that's it.

---

*built with claude sonnet 4.6 · feb 2026*
