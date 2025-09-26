# 📄 JSON Path Format

A simple, versioned JSON format lets you ship paths and edit them outside the game.

```json
{
  "name": "base_flythrough",
  "version": 1,
  "interpolation": "BEZIER",
  "loop": false,
  "constantSpeed": true,
  "keyframes": [
    {
      "tick": 0,
      "pos": [100.5, 72.0, -45.25],
      "yaw": 0.0,
      "pitch": 10.0,
      "roll": 0.0,
      "fov": 90.0,
      "easeIn": 0.1,
      "easeOut": 0.3,
      "handles": {
        "in":  [0.0, 0.0, 0.0],
        "out": [2.0, 0.5, -1.0]
      },
      "meta": { "note": "Spawn intro" }
    }
  ],
  "meta": {
    "author": "TysonTheEmber",
    "createdAt": "2025-09-26T00:00:00Z"
  }
}
```

> **Note:** Field names and availability may differ depending on your build. Treat this as the canonical *shape* to target in tools.
