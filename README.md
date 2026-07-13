# Vector Lab

**Live demo: https://kushk-physik.github.io/vector-lab/**

A single-file 3D tool for building intuition about spherical coordinates, rotations, and reflections. Define a vector by (r, θ, φ), transform it, and watch the angles update in real time in an actual 3D scene. No build step, no dependencies beyond Three.js loaded from a CDN.

![Vector Lab screenshot](screenshot.png)

## Try it

Open the [live demo](https://kushk-physik.github.io/vector-lab/) in any browser — nothing to install. Or grab `index.html` and open it locally; it's fully self-contained.

## What it does

- Define a vector by magnitude `r`, polar angle `θ` (measured from +Z), and azimuthal angle `φ` (in the XY-plane, from +X toward +Y) — the usual physics convention.
- Rotate the vector about X, Y, Z, or a custom axis and watch θ/φ recompute live.
- Reflect the vector across the XY, YZ, XZ, or a custom plane.
- Rotate the whole reference frame (axes + vector) about its current axes, not the original ones, so repeated rotations behave the way you'd expect.
- Once the frame is rotated, the original X/Y/Z axes stay as dashed reference lines while the new axes (solid, X′/Y′/Z′) show where things ended up.
- A small inset gizmo always shows the original orientation, so you don't lose track of where you started.
- Angle arcs drawn directly on the vector for θ and φ.
- Direction-angle arcs traced right on the guide sphere itself, from the tip of p to the +X, +Y, and +Z points — each one shows the angle p makes with that axis, so tracing the arc is tracing the angle.
- An optional second vector q, for comparing against p: dot product, the angle between them, and a live cross-product arrow.
- Drag the tip of the vector directly in the 3D scene to change its direction, instead of only using the θ/φ sliders.
- Quick presets (±X/±Y/±Z, random vector) and a share-link button that encodes the whole current state into the URL.
- An optional panel showing the frame's live rotation matrix and quaternion.
- Undo for the last action.
- Scale, normalize, negate helpers.
- Orbit camera: drag to rotate, scroll to zoom, right-drag to pan.
- Mobile-friendly layout: below ~720px wide, the control and stats panels collapse into slide-in drawers (☰ and 🧭 buttons) so the 3D scene isn't buried under fixed panels on a phone.

## Why this exists

This came out of my own research, where I kept running into vector rotations, reflections, and angle transformations in spherical coordinates. Working them out on paper with rotation matrices is straightforward enough, but it's much easier to reason about them — and to catch mistakes — when you can actually see the transformation happen instead of just trusting the algebra. So I built this as a tool I could reach for whenever I needed to visualize a vector transformation in spherical coordinates, rather than working it out by hand each time.

## Built with

Plain HTML/CSS/JS and [Three.js](https://threejs.org/) (r134, via jsDelivr). No framework, no package manager.

## Usage

1. Set r, θ, φ under "Vector p" and click "Set Vector p".
2. Use "Rotate p" / "Reflect p" to transform the vector against the fixed axes.
3. Use "Rotate Frame" to rotate the axes and vector together — watch the gizmo and the dashed original axes for reference.
4. "Undo Last Action" steps back one operation at a time.

## License

MIT, see [LICENSE](LICENSE).
