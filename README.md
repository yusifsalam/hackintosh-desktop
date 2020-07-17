# Desktop hackintosh with OpenCore

### Status: Maintenance

Compatibility is great, as the hardware closely resembles that of iMac 18,3. Onboard audio isn't configured, since I use a USB DAC. Wi-Fi and bluetooth are supported natively, so AirDrop and Continuity work out of the box.

Currently running:

| Component      | Version |
| -------------- | ------- |
| macOS Catalina | 10.15.6 |
| OpenCore       | 0.5.9   |

## Hardware info

| Component   | Model                                 |
| ----------- | ------------------------------------- |
| Motherboard | ASUS MAXIMUS HERO VIII                |
| CPU         | Intel i7-7700K Kaby Lake              |
| Memory      | 16GB 3200Mhz                          |
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

| Kext               | Version | Remark                 |
| ------------------ | ------- | ---------------------- |
| IntelMausiEthernet | 2.5.1d1 | Fixes ethernet         |
| Lilu               | 1.4.5   |                        |
| NVMEFix            | 1.0.3   | Fix for NVME SSDs      |
| USBMap             | -       | Inject only mapped USB |
| VirtualSMC         | 1.1.4   | SMC chip emulation     |
| WhateverGreen      | 1.4.0   | Graphics               |

## ACPI patches

| Patch        | Remark                     |
| ------------ | -------------------------- |
| SSDT-EC-USBX | Embedded Controller Rename |
| SSDT-PLUG    | x86 plugin injection fix   |
