# 🛠 Developer Integration

## Server → Client flow
You build an `ImmersiveMessage` server-side and pass it to `EmbersTextAPI.sendMessage(ServerPlayer, ImmersiveMessage)`.
The API packs it and ships it to the client over a `SimpleChannel` where it renders.

```java
void announce(ServerPlayer player, String text) {
    var msg = ImmersiveMessage.builder(120f, text)
        .anchor(TextAnchor.TOP_CENTER)
        .offset(0f, 6f)
        .gradient(0xFFA000, 0xFFDD55)
        .background(true)
        .typewriter(1.5f, true)
        .shake(ShakeType.CIRCLE, 0.8f);
    EmbersTextAPI.sendMessage(player, msg);
}
```

## Positioning & layout
- `anchor(TextAnchor)` sets where on the **screen** the message is anchored (e.g., `TOP_LEFT`, `CENTER_CENTER`).
- `align(TextAnchor)` sets **text alignment** relative to that anchor.
- `offset(float x, float y)` nudges from the anchor in pixels.
- `scale(float size)` or `size` (NBT) scales the text.
- `wrap(int width)` wraps long text to a pixel width.

## Color & style
- `color(int/String/ChatFormatting)` — single color by RGB, hex string, or vanilla color.
- `gradient(int... or String...)` — any number of gradient stops.
- Vanilla flags are supported via NBT (`bold`, `italic`, `underlined`, `strikethrough`, `obfuscated`).

## Backgrounds
Two approaches:
1) **Frame background** (tooltip-style): `background(true)` and optionally `bgColor`, `bgGradient`, `borderColor`, `borderGradient`, `bgAlpha`.
2) **Textured background quad**: `textureBackground(...)` + controls
   like `textureBackgroundScale(...)`, `textureBackgroundPadding(...)`,
   `textureBackgroundSize/Width/Height(...)`, and `textureBackgroundMode(...)`
   for stretch vs crop vs tile behavior.

## Animation
- `typewriter(float speed [, boolean centerWhileRevealing])`
- Whole‑text shakes: `shake(ShakeType, float)` where `ShakeType` supports `WAVE`, `CIRCLE`, `RANDOM`.
- Per‑character shakes: `charShake...` variants or NBT (`charShakeWave`, `charShakeCircle`, `charShakeRandom`).
- Obfuscation reveal: `obfuscate` mode (`LEFT`, `RIGHT`, `CENTER`, `RANDOM`) with optional `obfuscateSpeed` (NBT).

## Fonts
- Put your font assets at `assets/emberstextapi/font/` (JSON + font file).
- Reference them from text styles or NBT: `{font:"modid:font_name"}`.
