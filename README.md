# Cubot P50 (`marlon`) ROM Releases & OTA Manifests

> Unified release hub, OTA update manifests, and changelogs for Cubot P50 (`marlon` / MT6765) custom ROMs.

## What is this?
This repository hosts machine-readable OTA manifests (`OTA/{variant}/{rom}.json`), changelogs, and GitHub release tags for custom Android builds targeting the **Cubot P50 (`marlon`)**. Large `target-files` incremental OTA baselines are mirrored on SourceForge under [`cubot-marlon-rom-releases`](https://sourceforge.net/projects/cubot-marlon-rom-releases/).

## Features
- Per-ROM OTA JSON endpoints (`axion.json`, `lineage.json`, `derpfest.json`, `infinityx.json`) under `OTA/GMS/` and `OTA/VANILLA/`
- Built-in AxionOS Updater integration via `lineage.updater.uri`
- Incremental OTA tracking (`target_files` SHA-256 + SourceForge baseline links)
- Companion partition images (`boot.img`, `dtbo.img`, `recovery.img`, `vbmeta.img`, `super_empty.img`) and `SHA256SUMS.txt` on every release

## Installation

### Fastboot / Clean Install
```bash
fastboot flash boot boot.img
fastboot flash dtbo dtbo.img
fastboot flash recovery recovery.img
fastboot flash vbmeta vbmeta.img --disable-verity --disable-verification
fastboot reboot recovery
```

### Recovery (ADB Sideload)
1. In recovery, run **Factory Reset** -> **Format data / factory reset** (first install only).
2. Select **Apply update** -> **Apply from ADB**.
3. Sideload the ROM zip:
```bash
adb sideload <rom-package>.zip
```
4. Reboot system.

## Usage
Configure device Updater URI in ROM device trees with:
```makefile
PRODUCT_SYSTEM_PROPERTIES += \
    lineage.updater.uri=https://raw.githubusercontent.com/kelexine/cubot-marlon-rom-releases/main/OTA/{variant}/axion.json
```

## Architecture
```text
cubot-marlon-rom-releases/
├── OTA/
│   ├── GMS/
│   │   └── axion.json
│   └── VANILLA/
│       └── axion.json
└── changelogs/
    └── axion.md
```

## Contributing
- Follow Conventional Commits (`<type>(<scope>): <summary>`).
- Sign off all commits (`git commit -s`).

## License
Apache-2.0
