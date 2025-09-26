# 🚀 Install & Build

## Requirements
- **Java 17+**
- **Forge 1.20.1**
- **Gradle Wrapper** included

## Clone & Build
```bash
git clone https://github.com/TysonTheEmber/Aperture-API.git
cd Aperture-API
./gradlew assemble
```

### Dev Client
```bash
./gradlew runClient
```

### Lint & Format
```bash
./gradlew spotlessApply check
```

### Local Maven (optional)
If you want to consume the API from another project via Maven Local:
```bash
./gradlew publishToMavenLocal
```
Then depend on it from your other mod (coordinates depend on your published group/artifact/version).

> Tip: Alternatively, add this repo as a **composite build** in your main mod and use `includeBuild("../Aperture-API")`.
