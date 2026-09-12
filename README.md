<div align="center">

# OrangeFox Recovery for Infinix Hot 60i

### Device tree for **Infinix X6730**

![Status](https://img.shields.io/badge/status-work%20in%20progress-orange?style=for-the-badge)
![Recovery](https://img.shields.io/badge/recovery-OrangeFox-ff7900?style=for-the-badge)
![Device](https://img.shields.io/badge/device-X6730-blue?style=for-the-badge)

</div>

---

## Overview

This repository contains the device configuration used to build **OrangeFox Recovery Project** for the **Infinix Hot 60i (X6730)**.

> [!WARNING]
> This tree is a work in progress. Do not flash builds until the required device values have been verified against stock firmware and tested on the exact X6730 variant.

## Status

- [ ] Stock firmware properties verified
- [ ] Partition layout verified
- [ ] Kernel/prebuilt recovery image added
- [ ] Recovery builds successfully
- [ ] Touch and display tested
- [ ] ADB tested
- [ ] Storage and decryption tested
- [ ] Backup and restore tested
- [ ] Flashing tested

## Repository layout

```text
.
├── AndroidProducts.mk
├── BoardConfig.mk
├── device.mk
├── extract-files.sh
├── omni_X6730.mk
├── recovery/
├── rootdir/
└── vendorsetup.sh
```

The exact contents may change while the tree is being brought up.

## Build

Initialize an OrangeFox-compatible Android recovery source tree, then clone this repository into the device path:

```bash
git clone https://github.com/hypercleric/device_infinix_X6730.git \
  device/infinix/X6730
```

Set up the build environment and select the product:

```bash
source build/envsetup.sh
lunch omni_X6730-eng
mka recoveryimage
```

> The lunch target and build command must match the product makefile and the OrangeFox/Android branch being used.

## Bring-up checklist

Before publishing a flashable build, confirm the following from the device or matching stock firmware:

- Device codename and product identifiers
- SoC/platform and architecture
- Boot header version and page size
- Dynamic-partition and A/B configuration
- Recovery-as-boot or dedicated recovery layout
- Partition names, sizes, and filesystem types
- Kernel command line and DTB/DTBO requirements
- Encryption method and metadata partition
- Screen resolution, brightness path, and touch input

Never copy partition values from a similar device without verifying them on the X6730.

## Contributing

Issues and pull requests are welcome. Please include the exact firmware build, region/variant, relevant logs, and a clear description of what was tested. Remove serial numbers and other personal data before sharing logs.

## Disclaimer

Flashing custom recovery software can cause data loss or make a device unbootable. You are responsible for verifying images and maintaining a complete stock-firmware backup. This project is not affiliated with Infinix or the OrangeFox Recovery Project.

## Credits

- [OrangeFox Recovery Project](https://orangefox.download/)
- Android open-source recovery community
- Infinix Hot 60i testers and contributors
