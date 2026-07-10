# SUMI 墨 — a sumi-e nightmare

A complete single-file **Three.js horror game**: a Slender-style page hunt through a dark,
hand-drawn anime forest painted in sumi-e ink.

Open **`index.html`** in any modern browser (or serve the folder with any static server) and play.
Everything — world, art, UI, and audio — is generated procedurally at runtime in one file;
the only network dependency is the Three.js module loaded from CDN.

## The game

You are lost inside an ink painting. **Collect the 8 hand-drawn pages** scattered across
the forest's landmarks — a torii gate, a stone lantern, an old well, a twisted great tree,
a rock circle, a fallen log, a small shrine, and a row of graves.

Something ink-black wearing a **white noh mask** lives between the trees.

- Every page you take, it teleports closer and hunts faster.
- **Looking at it feeds the ink**: screen static, ink-splatter vignette, and audio
  distortion build while it is in view. Stare too long and it takes you — jumpscare, death.
- It never moves while watched. It drifts toward you when it is not.
- If it reaches you, it takes you anyway.

Collect all 8 pages to step out of the painting at dawn.

## Controls

| Key | Action |
|---|---|
| `WASD` / arrows | walk |
| `SHIFT` | sprint (drains stamina) |
| mouse | look |
| `E` | take a page |
| `F` | flashlight on/off |

## Difficulty

- **a bad dream** (easy) — he is patient; pages glow bright.
- **a nightmare** (normal) — he is hungry.
- **a haunting** (hard) — he is close; dim pages, faster teleports, he creeps while unseen.
- **the ink itself** (nightmare) — awake from the first step, no page glow, weak flashlight.

## How it's made

- **Cel shading** via `MeshToonMaterial` with a 4-band gradient map, thick ink-brush
  outlines by inverted-hull shells pushed along vertex normals, desaturated
  pastel-on-dark palette, canvas-painted night sky with a brushed moon.
- **Procedural forest**: instanced scraggly pines, broadleaf blobs and dead trees with
  hash-noise vertex displacement, ink-brush grass billboards, fireflies, exponential fog.
- **Hand-drawn everything**: the 8 page drawings, the noh masks (calm and screaming),
  the ink-splatter vignette, and the wobbly speech-bubble UI are all drawn on canvases
  at runtime — no image assets.
- **Procedural Web Audio**: wind (filtered noise), heartbeat that tracks danger, static
  hiss + electrical buzz while he's watched, master lowpass "distortion" as the ink rises,
  koto plucks on page pickup (hirajōshi scale), dread stings, footsteps, and a layered
  scream for the jumpscare — no audio files.
