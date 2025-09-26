# 🛠 Editor & Gizmos

Open the in‑game editor via its keybind (see **Config & Keybinds**). The editor shows a **timeline** and a **world overlay** with keyframes and Bezier handles.

## Keyframes
- **Add**: click in the world or use the `+` in the timeline
- **Move**: drag in the overlay; ticks update in the timeline
- **Delete**: select a keyframe and press delete / context menu

## Bezier Handles
- Each keyframe has up to two handles (in / out)
- Drag handles to tune curvature and ease
- The editor will **auto‑switch** the segment to Bezier when a handle is moved

## Interpolation per Segment
Choose the interpolation for a segment:
- **Bezier** – freeform curvature using handles
- **Catmull‑Rom** – natural, smooth spline through points
- **Cosine / Linear / Step** – alternative feels for cuts or holds

## Preview Controls
- **Play / Pause**: preview the camera
- **Scrub**: drag the time marker on the timeline
- **Speed**: preview at 0.5x, 1x, 2x
- **Show Path**: toggle path visualization

## Tips
- Use short **eased ramps** to avoid hard starts/ends
- Toggle **constant‑speed** if distances between keyframes vary
- Keep handles roughly **co‑planar** for flatter arcs
