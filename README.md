# Hackintosh EFI for Gigabyte Z390M Gaming + i7-9700K + Sapphire Radeon 5500 XT

<div align="left">
  <a href="README.md">English</a> |
  <a href="README_CN.md">中文</a>
</div>


This repository contains the OpenCore EFI configuration for a Hackintosh build with the following specifications. The configuration has been upgraded to OpenCore 1.0.4 and is compatible with macOS Sonoma 14.7.5.

## Hardware Specifications

- **Motherboard**: Gigabyte Z390M Gaming
- **CPU**: Intel Core i7-9700K
- **GPU**: Sapphire AMD Radeon RX 5500 XT
- **RAM**: 64GB
- **Storage**: 1TB
- **Network**: Intel Ethernet (Using IntelMausi.kext)
- **Wi-Fi/Bluetooth**: Broadcom BCM94360 (Drivers implemented using OpenCore Legacy Patcher)

## OpenCore Configuration

- OpenCore Version: 1.0.4 (Upgraded from previous version)
- macOS Compatibility: macOS Sonoma 14.7.5

## What Works

- CPU Power Management
- GPU Acceleration
- Audio (AppleALC)
- Ethernet
- Wi-Fi and Bluetooth
- USB Ports (Custom mapped)
- Sleep/Wake
- Thunderbolt 3 (SSDT-TB3)

## Included Files

### ACPI
- SSDT-AWAC.aml - Fix for 300-series RTC
- SSDT-DMAR.aml - DMAR table fix
- SSDT-DTPG.aml - DTPG fix
- SSDT-EC-USBX-DESKTOP.aml - Embedded Controller and USB power fix
- SSDT-GPRW.aml - Sleep/wake fix
- SSDT-PLUG-DRTNIA.aml - CPU power management
- SSDT-PMC.aml - NVRAM fix for 300-series
- SSDT-SBUS-MCHC.aml - SMBus fix
- SSDT-TB3.aml - Thunderbolt 3 support

### Kexts
- AMFIPass.kext - AMFI bypass
- AirportBrcmFixup.kext - Broadcom Wi-Fi support (via OpenCore Legacy Patcher)
- AppleALC.kext - Audio support
- CPUFriend.kext - CPU power management
- CPUFriendDataProvider.kext - CPU power management data
- CpuTscSync.kext - CPU TSC synchronization
- HibernationFixup.kext - Hibernation support
- IO80211FamilyLegacy.kext - Wi-Fi support (via OpenCore Legacy Patcher)
- IOSkywalkFamily.kext - Wi-Fi/Bluetooth support (via OpenCore Legacy Patcher)
- IntelMausi.kext - Intel Ethernet support
- Lilu.kext - Patching framework
- NVMeFix.kext - NVMe drive support
- RestrictEvents.kext - System update fixes
- SMCProcessor.kext - CPU monitoring
- SMCSuperIO.kext - Hardware monitoring
- USBMap.kext - Custom USB port mapping
- VirtualSMC.kext - SMC emulation
- WhateverGreen.kext - Graphics support

### Drivers
- HfsPlus.efi - HFS+ filesystem support
- OpenCanopy.efi - GUI boot menu
- OpenRuntime.efi - Runtime services
- ResetNvramEntry.efi - NVRAM reset option

## Installation

1. Mount your EFI partition
2. Backup your existing EFI folder if you have one
3. Copy the EFI folder from this repository to your EFI partition
4. Adjust the config.plist as needed for your specific hardware
5. Generate new SMBIOS information using GenSMBIOS or similar tools

## Post-Installation

- Generate unique SMBIOS information
- Verify that all hardware components are working correctly
- Adjust CPU power management if needed
- Test sleep/wake functionality

## Notes

- This EFI is configured specifically for the hardware mentioned above
- You may need to adjust settings for different hardware configurations
- Always keep a backup of your working EFI before making changes
- This configuration has been upgraded to OpenCore 1.0.4, which includes stability improvements and new features
- Tested and working with macOS Sonoma 14.7.5
- Wi-Fi and Bluetooth drivers are implemented using OpenCore Legacy Patcher to ensure compatibility with macOS Sonoma

## Credits

- [Acidanthera](https://github.com/acidanthera) for OpenCore and many kexts
- [Dortania](https://dortania.github.io/) for OpenCore guides
- [Dortania OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/) for comprehensive installation instructions
- [seven-of-eleven's Designare Z390 OpenCore EFI](https://github.com/seven-of-eleven/designare-z390-opencore-efi) for reference configuration
- [OpenCore Legacy Patcher Team](https://github.com/dortania/OpenCore-Legacy-Patcher) for Wi-Fi and Bluetooth support in macOS Sonoma
- All other developers who contributed to the Hackintosh community

## Disclaimer

This EFI configuration is provided as-is without any warranty. Use at your own risk.
