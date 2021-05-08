# Desktop hackintosh with OpenCore

### Status: Maintenance

Two config files are provided - one for system with a dedicated GPU and another one for iGPU only.

Compatibility is great, as the hardware closely resembles that of iMac 18,1 or 18,3. Onboard audio isn't configured, since I use a USB DAC. Wi-Fi and bluetooth are supported natively, so AirDrop and Continuity work out of the box.

Currently running:

| Component     | Version        |
| ------------- | -------------- |
| macOS version | 11.2.3 (20D91) |
| OpenCore      | 0.6.8          |

## Hardware info

| Component   | Model                                 |
| ----------- | ------------------------------------- |
| Motherboard | ASUS MAXIMUS HERO VIII                |
| CPU         | Intel i7-7700K Kaby Lake              |
| Memory      | 32GB 3200Mhz                          |
| Storage     | Kingston A2000 1TB                    |
| GPU         | PowerColor Radeon RX 5700XT Red Devil |
| Audio       | NuForce µDAC 2                        |
| WLAN        | Fenvi FV-T919                         |

## Status

### Working

- [x] Ethernet
- [x] iCloud services - iMessage, FaceTime, AppStore
- [x] GPU acceleration
- [x] Bluetooth
- [x] Wi-Fi
- [x] AirDrop, Continuity
- [x] Mac-like booting interface for multiboot
- [x] Sleep/wake
- [x] Native CPU power management

### Not tested

- [ ] Sidecar
- [ ] FileVault
- [ ] Thunderbolt

## Kexts

| Kext          | Version | Remark                 |
| ------------- | ------- | ---------------------- |
| IntelMausi    | 1.0.6   | Fixes ethernet         |
| Lilu          | 1.5.3   | Patch engine           |
| NVMEFix       | 1.0.7   | Fix for NVME SSDs      |
| USBMap        | -       | Inject only mapped USB |
| VirtualSMC    | 1.2.3   | SMC chip emulation     |
| WhateverGreen | 1.4.9   | Graphics               |

## ACPI patches

| Patch        | Remark                     |
| ------------ | -------------------------- |
| SSDT-EC-USBX | Embedded Controller Rename |
| SSDT-PLUG    | x86 plugin injection fix   |

## DRM

To fix broken AppleTV+, run `defaults write com.apple.AppleGVA gvaForceAMDKE -boolean yes` in the terminal. This setting enables the AMD GPU hardware decoder.

DRM does not work in Safari as of Big Sur, but works in Chromium-based browsers and browsers that use software-based DRM, so Netflix will work in Chrome but not Safari.

Note that the DRM fix will probably break your built-in screen recording, to fix you can run `defaults write com.apple.AppleGVA gvaForceAMDKE -boolean no` which disables the DRM fix.
