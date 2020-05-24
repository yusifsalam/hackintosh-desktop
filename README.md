# Desktop hackintosh with OpenCore

### Status: Maintenance

Compatibility is great, as the hardware closely resembles that of iMac 18,3. Onboard audio isn't configured, since I use a USB DAC. I don't have a wireless card attached, so AirDrop, Continuity, Handoff and other similar features are not working.

Currently running:

| Component      | Version |
| -------------- | ------- |
| macOS Catalina | 10.15.4 |
| OpenCore       | 0.5.8   |

## Hardware info

| Component   | Model                                 |
| ----------- | ------------------------------------- |
| Motherboard | ASUS MAXIMUS HERO VIII                |
| CPU         | Intel i7-7700K Kaby Lake              |
| Memory      | 16GB 3200Mhz                          |
| Storage     | Kingston A2000 1TB                    |
| GPU         | PowerColor Radeon RX 5700XT Red Devil |
| Audio       | NuForce µDAC 2                        |
| WLAN        | -                                     |

## Status

### Working

- [x] Ethernet
- [x] iCloud services - iMessage, FaceTime, AppStore
- [x] GPU acceleration
- [x] Bluetooth (via USB dongle)
- [x] Mac-like booting interface for multiboot
- [x] Sleep/wake
- [x] Native CPU power management

### Not tested

- [ ] Sidecar
- [ ] FileVault
- [ ] Thunderbolt

## Kexts

| Kext               | Version | Remark                 |
| ------------------ | ------- | ---------------------- |
| IntelMausiEthernet | 2.5.1d1 | Fixes ethernet         |
| Lilu               | 1.4.4   |                        |
| NVMEFix            | 1.0.2   | Fix for NVME SSDs      |
| USBMap             | -       | Inject only mapped USB |
| VirtualSMC         | 1.1.3   | SMC chip emulation     |
| WhateverGreen      | 1.3.9   | Graphics               |

## ACPI patches

| Patch        | Remark                     |
| ------------ | -------------------------- |
| SSDT-EC-USBX | Embedded Controller Rename |
| SSDT-PLUG    | x86 plugin injection fix   |
