# 🎯 Follow Entity & Look-At

### Follow an entity (position constraint)
```java
ApertureAPI.follow(path, entity); // binds path to entity transform each tick
```

### Look‑At a point/entity (orientation constraint)
```java
ApertureAPI.lookAt(path, targetPosOrEntity);
```

Use soft damping to avoid jitter if the target moves erratically.
