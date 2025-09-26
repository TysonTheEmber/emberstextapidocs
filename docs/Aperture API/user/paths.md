# 🧭 Paths & Interpolation

A **path** is a sequence of **keyframes** (tick, position, rotation, optional FOV) with an interpolation mode per segment.

## Interpolation Modes
- **Bezier** – shape the curve with handles; best for artistic moves
- **Catmull‑Rom** – passes through keyframes; great for natural motion
- **Cosine** – smooth step interpolation (S‑curve feel)
- **Linear** – straight lines between points
- **Step** – hard cuts & holds

## Easing
Per‑keyframe easing helps avoid abrupt velocity changes. A typical approach is to specify `easeIn` and `easeOut` (0.0–1.0).

## Constant‑Speed Playback
Long segments will otherwise run faster than short ones at the same tick count. The engine can **re‑parameterize by arc‑length** to normalize speed visually.

> **Tip:** If the beginning looks “snappy,” add a **lead‑in segment** or increase ease‑out on the first keyframe.
