# ❓ FAQ & Troubleshooting

**The camera “jumps” at a keyframe.**  
Use **easing** or add a short buffer segment. For Bezier, keep handles aligned with the desired tangent.

**Speed feels inconsistent between segments.**  
Enable **constant‑speed** mode or add more keyframes to even out distances.

**Nothing happens when I run `/camera play`.**  
Check permissions/targets, ensure the path exists, and verify no conflicting camera mods are active.

**Can I run this server‑side only?**  
Playback requires client visuals; server‑only makes sense for **export and path management**. Ship the mod client‑side for editor/preview.
