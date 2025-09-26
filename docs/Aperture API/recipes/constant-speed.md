# 🏎️ Constant-Speed Playback

Problem: Segments of unequal length produce uneven camera speed.  
Solution: Reparameterize by **arc‑length**.

```java
var path = ApertureAPI.path(PathType.CATMULL_ROM)
    .add(0,  p0, yaw0, pitch0)
    .add(40, p1, yaw1, pitch1)
    .add(80, p2, yaw2, pitch2)
    .constantSpeed(true);
```

Tips:
- Keep keyframe spacing semiregular where possible
- Prefer Catmull‑Rom for natural sweeps; Bezier for stylized shots
