# 🔌 Integrating the API

You can consume Aperture‑API from another mod either as a **composite build** or after publishing to **Maven Local**.

## Composite Build (recommended during development)
**settings.gradle**
```kts
includeBuild("../Aperture-API")
```

**build.gradle**
```gradle
dependencies {
    implementation fg.deobf("net.tysontheember:Aperture-API")
}
```

> Coordinates may vary depending on `group`/`version`. For a released artifact, replace with the published coordinate.

## Minimal Usage Pattern
```java
import net.tysontheember.apertureapi.api.ApertureAPI;
import net.tysontheember.apertureapi.api.PathType;

// Create and play a simple path
var builder = ApertureAPI.path(PathType.CATMULL_ROM)
    .add(0,  pos0, yaw0, pitch0)
    .add(40, pos1, yaw1, pitch1)
    .add(80, pos2, yaw2, pitch2)
    .constantSpeed(true);

ApertureAPI.play(player, builder.build(), 1.0f, false, true);
```
