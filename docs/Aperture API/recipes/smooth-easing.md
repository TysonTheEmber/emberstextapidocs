# 🎬 Smooth Entrances & Exits

Use small **ease‑in/out** values to ramp motion at segment boundaries.

```java
b.add(0, p0, yaw0, pitch0).easeOut(0.25f);
b.add(40, p1, yaw1, pitch1).easeIn(0.25f).easeOut(0.25f);
b.add(80, p2, yaw2, pitch2).easeIn(0.25f);
```

Combine with Bezier handles for film‑like arcs.
