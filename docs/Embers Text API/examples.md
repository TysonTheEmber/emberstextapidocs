# 💡 Examples

## 1) Boss Intro (centered typewriter with wave shake)
```java
var msg = ImmersiveMessage.builder(200f, "🔥 IGNIS, INFERNO KNIGHT 🔥")
    .anchor(TextAnchor.CENTER_CENTER)
    .gradient(0xFF2A00, 0xFFA500)
    .background(true)
    .typewriter(2.0f, true)
    .shake(ShakeType.WAVE, 1.0f);
server.getPlayerList().getPlayers().forEach(p -> EmbersTextAPI.sendMessage(p, msg));
```

## 2) Fixed‑size textured panel (don’t stretch, crop to 3:1)
```mclang
/emberstextapi sendcustom @a {
  textureBackground:{texture:"mymod:textures/gui/boss_panel.png",mode:"CROP",sizeX:180,sizeY:60,paddingX:8,paddingY:6},
  wrap:160, anchor:"TOP_CENTER", offsetY:10, background:false, 
  gradient:["#FF3A00","#FFC800"], typewriter:1.5, center:true
} 140 "SCYLLA AWAKENS"
```

## 3) Minimal single‑color message at top
```java
var msg = ImmersiveMessage.builder(80f, "Server restarting soon…")
    .anchor(TextAnchor.TOP_CENTER)
    .color(0xFFFF55)
    .background(true);
EmbersTextAPI.sendMessage(player, msg);
```

## 4) Per‑character random jitter + obfuscation reveal
```mclang
/emberstextapi sendcustom @p {
  obfuscate:"RANDOM", obfuscateSpeed:0.08, charShakeRandom:0.7,
  gradient:["#A0A0A0","#FFFFFF"], anchor:"BOTTOM_CENTER", offsetY:-30
} 120 "Decrypting Access Key…"
```
