# 🧰 Command Hooks (Brigadier)

Aperture integrates cleanly with Brigadier. Here’s how to register a simple wrapper command in your mod that triggers a path:

```java
dispatcher.register(Commands.literal("demo_shot")
    .requires(src -> src.hasPermission(2))
    .executes(ctx -> {
        var player = ctx.getSource().getPlayerOrException();
        var path = ApertureAPI.path(PathType.BEZIER)
            .add(0, player.position(), player.getYRot(), player.getXRot())
            .add(60, player.position().add(12, 6, -3), player.getYRot()+40, player.getXRot());
        ApertureAPI.play(player, path.build(), 1.0f, false, true);
        return 1;
    }));
```

You can also forward to the stock `/camera` command from dialogs, quests, or scripts.
