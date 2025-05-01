# 技嘉 Z390M Gaming + i7-9700K + 蓝宝石镭龙 5500 XT 的黑苹果 EFI

<div align="right">
  <a href="README.md">English</a> |
  <a href="README_CN.md">中文</a>
</div>

本仓库包含适用于以下规格黑苹果构建的 OpenCore EFI 配置。该配置已升级到 OpenCore 1.0.4 版本，并兼容 macOS Sonoma 14.7.5。

## 硬件规格

- **主板**: 技嘉 Z390M Gaming
- **处理器**: Intel Core i7-9700K
- **显卡**: 蓝宝石 AMD 镭龙 RX 5500 XT
- **内存**: 64GB
- **存储**: 1TB
- **网络**: Intel 以太网 (使用 IntelMausi.kext)
- **无线网络/蓝牙**: 博通 BCM94360 (驱动通过 OpenCore Legacy Patcher 实现)

## OpenCore 配置

- OpenCore 版本: 1.0.4 (从之前版本升级)
- macOS 兼容性: macOS Sonoma 14.7.5

## 正常工作的功能

- CPU 电源管理
- GPU 加速
- 音频 (AppleALC)
- 以太网
- Wi-Fi 和蓝牙
- USB 端口 (自定义映射)
- 睡眠/唤醒
- 雷电 3 (SSDT-TB3)

## 包含的文件

### ACPI
- SSDT-AWAC.aml - 300系列RTC修复
- SSDT-DMAR.aml - DMAR表修复
- SSDT-DTPG.aml - DTPG修复
- SSDT-EC-USBX-DESKTOP.aml - 嵌入式控制器和USB电源修复
- SSDT-GPRW.aml - 睡眠/唤醒修复
- SSDT-PLUG-DRTNIA.aml - CPU电源管理
- SSDT-PMC.aml - 300系列NVRAM修复
- SSDT-SBUS-MCHC.aml - SMBus修复
- SSDT-TB3.aml - 雷电3支持

### 驱动程序(Kexts)
- AMFIPass.kext - AMFI绕过
- AirportBrcmFixup.kext - 博通Wi-Fi支持 (通过OpenCore Legacy Patcher)
- AppleALC.kext - 音频支持
- CPUFriend.kext - CPU电源管理
- CPUFriendDataProvider.kext - CPU电源管理数据
- CpuTscSync.kext - CPU TSC同步
- HibernationFixup.kext - 休眠支持
- IO80211FamilyLegacy.kext - Wi-Fi支持 (通过OpenCore Legacy Patcher)
- IOSkywalkFamily.kext - Wi-Fi/蓝牙支持 (通过OpenCore Legacy Patcher)
- IntelMausi.kext - Intel以太网支持
- Lilu.kext - 补丁框架
- NVMeFix.kext - NVMe驱动器支持
- RestrictEvents.kext - 系统更新修复
- SMCProcessor.kext - CPU监控
- SMCSuperIO.kext - 硬件监控
- USBMap.kext - 自定义USB端口映射
- VirtualSMC.kext - SMC模拟
- WhateverGreen.kext - 图形支持

### 引导驱动(Drivers)
- HfsPlus.efi - HFS+文件系统支持
- OpenCanopy.efi - 图形化引导菜单
- OpenRuntime.efi - 运行时服务
- ResetNvramEntry.efi - NVRAM重置选项

## 安装步骤

1. 挂载您的EFI分区
2. 如果您已有EFI文件夹，请先备份
3. 将本仓库中的EFI文件夹复制到您的EFI分区
4. 根据您的特定硬件需求调整config.plist
5. 使用GenSMBIOS或类似工具生成新的SMBIOS信息

## 安装后步骤

- 生成唯一的SMBIOS信息
- 验证所有硬件组件是否正常工作
- 如有需要，调整CPU电源管理
- 测试睡眠/唤醒功能

## 注意事项

- 此EFI专为上述硬件配置
- 对于不同的硬件配置，您可能需要调整设置
- 在进行更改前，请始终保留一份可用的EFI备份
- 此配置已升级到OpenCore 1.0.4版本，包含稳定性改进和新功能
- 已在macOS Sonoma 14.7.5上测试并正常工作
- Wi-Fi和蓝牙驱动通过OpenCore Legacy Patcher实现，以确保与macOS Sonoma的兼容性

## 致谢

- 感谢[Acidanthera](https://github.com/acidanthera)提供OpenCore和众多kexts
- 感谢[Dortania](https://dortania.github.io/)提供OpenCore指南
- 感谢[Dortania OpenCore安装指南](https://dortania.github.io/OpenCore-Install-Guide/)提供全面的安装说明
- 感谢[seven-of-eleven的Designare Z390 OpenCore EFI](https://github.com/seven-of-eleven/designare-z390-opencore-efi)提供参考配置
- 感谢[OpenCore Legacy Patcher团队](https://github.com/dortania/OpenCore-Legacy-Patcher)提供macOS Sonoma中的Wi-Fi和蓝牙支持
- 感谢所有为黑苹果社区做出贡献的开发者

## 免责声明

此EFI配置按原样提供，不提供任何保证。使用风险自负。
