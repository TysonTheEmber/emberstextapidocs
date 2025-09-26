# ⌨️ Command Reference

Root command: `/emberstextapi`

## Demo
```mclang
/emberstextapi test <id>
```
Plays a built‑in demonstration message.

## Send (basic)
```mclang
/emberstextapi send <player> <duration> <text>
```
Sends `<text>` to `<player>` for `<duration>` ticks.

## SendCustom (full control via NBT)
```mclang
/emberstextapi sendcustom <player> <nbt> <duration> <text>
```

### Common NBT Tags
```json
{
  "font": "modid:font_name",
  "bold": true, "italic": true, "underlined": false, "strikethrough": false, "obfuscated": false,
  "color": "#FFAA00",
  "gradient": ["#FF0000", "#00FF00"],
  "bgGradient": {"start":"#FF000080","end":"#0000FF80"},
  "borderGradient": ["#FF0000","#00FF00"],
  "bgColor": "#333333CC", "borderColor": "#FFFFFF", "bgAlpha": 0.5,
  "background": true,
  "textureBackground": {
    "texture": "modid:textures/gui/panel.png",
    "mode": "CROP",
    "sizeX": 120, "sizeY": 40,
    "paddingX": 6, "paddingY": 4,
    "scaleX": 0.5, "scaleY": 0.5
  },
  "size": 1.25,
  "typewriter": 2.0, "center": true,
  "wrap": 160,
  "obfuscate": "LEFT", "obfuscateSpeed": 0.1,
  "anchor": "CENTER_CENTER", "align": "CENTER_CENTER",
  "offsetX": 10, "offsetY": -20,
  "shadow": true,
  "shakeWave": 1.5, "charShakeRandom": 0.8
}
```

> **Tip:** Use `wrap`, `textureBackgroundSize*`, and `textureBackgroundMode` to control
> how text and background relate (fixed panels vs stretching).

### NBT equivalents (for `/sendcustom` and data‑driven use)
- `font` — resource location: `{font:"modid:font_name"}`
- `bold`, `italic`, `underlined`, `strikethrough`, `obfuscated` — style flags
- `color` — hex or name: `{color:"#FFAA00"}`
- `gradient` — list or `{start,end}`
- `bgGradient`, `borderGradient` — gradient objects/lists for frame background
- `bgColor`, `borderColor`, `bgAlpha` — solid frame colors + opacity
- `textureBackground` — either a string (`"modid:textures/gui/panel.png"`) or an object with fields:
  `texture`, `u`, `v`, `width`, `height`, atlas `textureWidth`, `textureHeight`,
  per‑axis `paddingX`, `paddingY`, `scaleX`, `scaleY`, draw size `sizeX`, `sizeY` (aka `drawWidth`, `drawHeight`),
  and `mode`/`resize` (Stretch/Crop/Tile).
- `size` — uniform text scale
- `typewriter` (float), optional `"center": true`
- `background` — boolean
- `wrap` — pixel width
- `obfuscate`, `obfuscateSpeed` — mode (+ optional speed)
- `anchor`, `align` — enum names as strings
- `offsetX`, `offsetY` — pixels
- `shadow` — boolean
- Shakes: `shakeWave`, `shakeCircle`, `shakeRandom`, `charShakeWave`, `charShakeCircle`, `charShakeRandom`

*Deprecated tag names still function but will log warnings.*
