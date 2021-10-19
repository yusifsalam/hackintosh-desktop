# Desktop hackintosh with OpenCore

### Status: Maintenance

Compatibility is great, as the hardware closely resembles that of iMac 18,1 or 18,3. Onboard audio isn't configured, since I use a USB DAC. Wi-Fi and bluetooth are supported natively, so AirDrop and Continuity work out of the box.

Currently running:

| Component     | Version     |
| ------------- | ----------- |
| macOS version | 12.0.1      |
| OpenCore      | 0.7.4       |

## Hardware info

| Component   | Model                    |
| ----------- | ------------------------ |
| Motherboard | ASUS MAXIMUS HERO VIII   |
| CPU         | Intel i7-7700K Kaby Lake |
| Memory      | 32GB 3200Mhz             |
| Storage     | Kingston A2000 1TB       |
| iGPU        | Intel HD 630             |
| Audio       | NuForce µDAC 2           |
| WLAN        | Fenvi FV-T919            |

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

## Kexts

| Kext          | Version | Remark                 |
| ------------- | ------- | ---------------------- |
| IntelMausi    | 1.0.7   | Fixes ethernet         |
| Lilu          | 1.5.6   | Patch engine           |
| NVMEFix       | 1.0.9   | Fix for NVME SSDs      |
| USBMap        | -       | Inject only mapped USB |
| VirtualSMC    | 1.2.7   | SMC chip emulation     |
| WhateverGreen | 1.5.4   | Graphics               |

## ACPI patches

| Patch        | Remark                     |
| ------------ | -------------------------- |
| SSDT-EC-USBX | Embedded Controller Rename |
| SSDT-PLUG    | x86 plugin injection fix   |
