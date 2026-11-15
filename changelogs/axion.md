# AxionOS (`marlon`) Changelog

## 2026-11-15 (`v2.9-20261115-erofs`)
- Switched dynamic super partitions (`system`, `vendor`, `product`) to **EROFS** (`lz4hc,9`, 256KiB pcluster) with `ext4` fallbacks.
- Linux `4.19.325` CIP SLTS kernel built with Android NDK r30 (`close_range`, `clone3`, `mremap(MREMAP_DONTUNMAP)`, `UFFDIO_CONTINUE`, `MEMCG`, `PSI`, `FUSE`).
- Enabled frozen `vendor.cubot.hardware.encore` AIDL v1 HAL and VINTF declarations.
- Wired `MarlonKeyHandler`, `mtk-tpd.kl` wake key mapping, DT2W settings sync, and lockscreen torch/camera gestures.
- Fixed `vendor.camera.aux.packagelist` property length violation.
