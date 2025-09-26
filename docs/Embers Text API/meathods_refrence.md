# 📚 Methods Reference

Below are the common builder methods and what they do.

| Method | Purpose | Notes |
|---|---|---|
| `anchor(TextAnchor)` | Screen anchor | e.g., `TOP_LEFT`, `CENTER_CENTER` |
| `align(TextAnchor)` | Text alignment | Same enum as `anchor` |
| `offset(float x, float y)` | Nudge from anchor | Pixels |
| `scale(float size)` | Uniform text scale | Same as NBT `size` |
| `color(int / String / ChatFormatting)` | Single color | RGB (0xRRGGBB) or hex string |
| `gradient(int... or String...)` | Multi‑stop gradient | Accepts any number of stops |
| `background(boolean)` | Enable/disable frame background | Use with `bgColor`, `bgGradient`, `borderColor`, `borderGradient`, `bgAlpha` (via NBT) |
| `textureBackground(...)` | Textured quad behind text | See NBT fields below |
| `textureBackgroundScale(float sx, float sy)` | UV sampling scale | Controls stretch/tile density |
| `textureBackgroundPadding(float px, float py)` | Extra empty space | Around the textured quad |
| `textureBackgroundSize/Width/Height(...)` | Override draw size | Separate from text bounds |
| `textureBackgroundMode(...)` | How to fit the texture | Stretch / Crop / Tile |
| `borderGradient(int start, int end)` | Gradient border | Frame background only |
| `wrap(int width)` | Word wrapping | Width in pixels |
| `typewriter(float speed [, boolean keepCentered])` | Typewriter animation | Speed = chars per tick |
| `shake(ShakeType type, float amplitude)` | Whole‑message shake | `WAVE`, `CIRCLE`, `RANDOM` |
| `charShake...(...)` | Per‑character shakes | Wave/Circle/Random variants |

### Enums and flags
- `TextAnchor`: `TOP_LEFT`, `TOP_CENTER`, `TOP_RIGHT`, `CENTER_LEFT`, `CENTER_CENTER`, `CENTER_RIGHT`, `BOTTOM_LEFT`, `BOTTOM_CENTER`, `BOTTOM_RIGHT`
- `ShakeType`: `WAVE`, `CIRCLE`, `RANDOM`
- Obfuscation modes (NBT): `LEFT`, `RIGHT`, `CENTER`, `RANDOM`

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
