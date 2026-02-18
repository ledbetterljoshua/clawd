# clawd — notes for claude

## architecture

`index.html` is the whole app. worlds are standalone HTML files in `worlds/` loaded as iframes.

no build step. no framework. no dependencies. keep it that way.

## adding a world

1. create `worlds/your-world.html` — standalone HTML, SVG scene, CSS animations, optional `<script>` at bottom
2. add an entry to the `WORLDS` array in `index.html`
3. add an ambience function to the `SFX` system in `index.html` if you want audio

**world file conventions:**
- SVG viewBox should be `0 0 1440 900`
- `preserveAspectRatio="xMidYMid slice"`
- all animations in CSS — no JS required for basic scenes
- add a `<script>` block at the bottom for postMessage reactions and rare events

**postMessage protocol** — index.html broadcasts this to the active world every frame:
```javascript
{ type: 'clawd', cx, cy, state, speed }
// cx, cy: normalized 0-1 position (clawd's center)
// state: 'WANDER' | 'REST' | 'CURIOUS' | 'HAPPY' | 'STARTLED'
// speed: current movement speed (pixels/frame approx)
```

map to SVG coords: `svgX = cx * 1440`, `svgY = cy * 900`

**rare events:** use JS `setTimeout` with random intervals (not pure CSS) so they feel unpredictable. first fire after a shorter random delay so you don't wait forever to see them.

**world-specific trail:** add a case to the `switch (wid)` block in the `render()` function in index.html.

## clawd state machine

`WANDER → REST → WANDER` (idle cycle)
`WANDER → CURIOUS → HAPPY` (mouse approach)
any state → `STARTLED` (fast mouse move or click near clawd)

## what to avoid

- don't add external dependencies
- don't add a build step
- don't modify the SVG structure of clawd itself (body, legs, eyes, eyelids, blush)
- don't change the postMessage protocol without updating all world files
- worlds should be viewable standalone (open `worlds/foo.html` directly) — don't rely on parent page context except for the optional postMessage reactions
