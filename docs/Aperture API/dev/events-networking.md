# 📡 Events & Networking

A typical integration needs to react to **start/stop** and optionally synchronize state to clients.

## Suggested Events
- `CameraPlayEvent` – fired when playback begins
- `CameraStopEvent` – fired when halted/reset
- `CameraTickEvent` – per‑tick progress callbacks

Handlers can:
- Pause/resume other UI elements
- Trigger audio/voice lines
- Fade HUD or letterboxing

> If you send custom packets, prefer lightweight, **id‑based path references** and let clients resolve JSON locally when possible.
