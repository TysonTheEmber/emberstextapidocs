# ⌨️ Commands

The command surface is intentionally small and focused.

## `/aperture`
- `help` – show help
- `version` – print API version
- `api` – developer info

## `/camera`
- `list` – list available paths
- `play <path> [speed] [loop] [auto-reset] [target]` – play a path for a player or selector
- `stop [target]` – stop camera
- `reset [target]` – reset player view
- `interpolation` – set default interpolation for new segments
- `export` – export the current/selected path to JSON

### Examples
```text
/camera list
/camera play base_flythrough 1.0 false true @p
/camera stop @a
/camera reset @p
```
