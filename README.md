# 🌃 Midnight City Drive

A free-drive 3D night-city driving game that runs entirely in the browser — no installs, no app store. Built with [Three.js](https://threejs.org/), playable on desktop or phone (with gyroscope steering), and deployable as a single static file.

Pick a car in a 3D showroom, drop into a neon-lit rainy city, follow the glowing coin trail through downtown, and dodge traffic along the way.

---

## Features

- **3D car showroom** — 4 hand-modeled cars (GT coupe, muscle car, cyber hypercar, roadster) on a rotating pedestal, each with different top speed / acceleration
- **Neon night city** — wet reflective roads, glowing signs, streetlights, blinking rooftop beacons, a full traffic grid of AI-driven cars
- **Coin route with GPS-style guidance** — a pulsing arrow + glowing road chevrons lead you to the next coin; turns behind you trigger a clear "TURN AROUND" indicator instead of an ambiguous arrow
- **Hybrid coin targeting** — collect coins in any order; the game intelligently guides you along the route or to the nearest missed coin
- **Live engine audio** — procedurally generated engine note that rises and falls with a 5-speed virtual gearbox, plus a synthwave background loop (or drop in your own MP3)
- **Speed dial HUD** — RPM arc, digital speedometer, gear indicator
- **Minimap** — roads, route, remaining coins, and traffic at a glance
- **Controls for every device** — phone tilt (gyroscope), on-screen pedals, drag-to-steer, or keyboard (arrow keys / WASD)

---

## Adding your own background music

The game automatically tries to load a file named **`music.mp3`** from the same folder as `index.html`. If it's missing, a generated synthwave loop plays instead — so this step is optional.

To use your own track:
1. Add an MP3 file to the repo root.
2. Rename it to `music.mp3`.
3. Commit and push. No code changes needed.

Use a track you have rights to use (royalty-free or your own recording) — this repo does not include or license any music.

---

## Controls

| Action | Phone | Desktop |
|---|---|---|
| Steer | Tilt phone (tap "Enable Tilt" first) or drag on screen | Arrow keys / A · D or drag on screen |
| Gas | Hold the **Gas** pedal | W or ↑ |
| Brake / Reverse | Hold the **Brake** pedal | S or ↓ |
| Reset car | "Reset Car" button | "Reset Car" button |
| Mute | "Sound" button | "Sound" button |

On Android, if the tilt button shows **"Tilt Blocked"**, check `Chrome → ⋮ → Settings → Site settings → Motion sensors → Allowed`, then reload.

---

## Project structure

```
.
├── index.html   # entire game — HTML, CSS, and JS in one file
└── README.md
```

Everything (3D city, cars, textures, audio) is generated procedurally in code at runtime — there are no external asset files except the optional `music.mp3`.

---

## Customizing

Most tunable values live near the top of the relevant section in `index.html`:

- **City size / block layout** — `B` (block size) and `GRID` (streets per axis)
- **Coin route** — the `route` array (list of `[x, z]` waypoints)
- **Car stats** — the `CARS` array (`top` = top speed, `accel` = acceleration)
- **Traffic count** — the loop that builds the `traffic` array
- **Steering sensitivity** — the `/ 20` divisor inside `handleOrientation()`

---

## Tech

- [Three.js r128](https://threejs.org/) (loaded via CDN, no bundler required)
- Vanilla JavaScript, HTML, CSS — no framework, no build tooling
- Web Audio API for procedural engine sound and synth music
- DeviceOrientation API for gyroscope steering

## License

Add your preferred license here (e.g. MIT) before publishing publicly.
