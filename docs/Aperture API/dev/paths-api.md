# 🧩 Working with Paths (API)

This page outlines common operations available from the API surface. Class names are representative and may differ slightly in your build.

## Builders
```java
PathBuilder b = ApertureAPI.path(PathType.BEZIER);
b.add(tick, position, yaw, pitch);
b.setFov(90f);          // optional per-keyframe
b.easeIn(0.2f).easeOut(0.4f);
b.handleIn(vec3).handleOut(vec3);
var path = b.build();
```

## Playback
```java
ApertureAPI.play(player, path, /*speed*/ 1.25f, /*loop*/ false, /*autoReset*/ true);
ApertureAPI.stop(player);
ApertureAPI.reset(player);
```

## Utilities
- **Reparameterize** for constant speed
- **Trim / Split** paths by tick range
- **Reverse** or **Loop** helpers
- **Look‑At** point or entity constraints
