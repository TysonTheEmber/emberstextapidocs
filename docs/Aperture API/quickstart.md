# ⚡ Quickstart

This minimal flow shows how to construct a path, add keyframes, and play it for a player. The types shown are **representative** of the public API surface.

```java
// Pseudo-API example showing common usage patterns.
import net.tysontheember.apertureapi.api.ApertureAPI;
import net.tysontheember.apertureapi.api.PathBuilder;
import net.tysontheember.apertureapi.api.PathType;

public class DemoCamera {
    public static void play(ServerPlayer player) {
        // 1) Build a BEZIER path with 3 keyframes
        PathBuilder path = ApertureAPI.path(PathType.BEZIER)
            .add(0,  player.position(),  player.getYRot(), player.getXRot())
            .add(40, player.position().add(10, 5, 0),   player.getYRot()+30, player.getXRot()-5)
            .add(80, player.position().add(0, 10, 10),  player.getYRot()+80, player.getXRot());

        // 2) Optional: Enable constant-speed reparameterization
        path.constantSpeed(true);

        // 3) Play the path at 1.0x speed for the player
        ApertureAPI.play(player, path.build(), 1.0f, /*loop=*/false, /*autoReset=*/true);
    }
}
```

### Exporting to JSON
```java
String json = ApertureAPI.exportJson(path.build());
Files.writeString(Path.of("my_path.json"), json);
```

### Playing back a JSON path (server command)
```text
/camera play my_path 1.0 false true @p
```
