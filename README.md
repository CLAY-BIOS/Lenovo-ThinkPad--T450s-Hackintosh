# Thinkpad T450s Catalina
-                          Macos BigSur 现已推出
- https://github.com/CLAY-BIOS/Lenovo-ThinkPad-T450s-Big-Sur-OpenCore                               
## 简介
- 这是一个完整的Thinkpad T450s macOS Catalina配置 （基于 @jsassu20 的T450配置）
- 由于T450s只有一条内存插槽（使用8GB以上内存时板载内存识别不正常）您需要注入内存信息
- 使用DW1820A时只需将驱动复制到kext 安装系统时无需在BIOS中禁用WIFI
- 音频问题请把CodecCommander.kext复制到 L / E 目录重建缓存修复权限 再执行修复脚本
- 由于acidanthera的驱动现在不会在CLOVER中做兼容性测试 可能会导致一些驱动出现问题 解决方法是把出现问题的驱动放入 L / E 目录下（例如：触摸板驱动 VoodooPS2Controller.kext）
-  触摸屏在10.14版本中得到原生支持 10.15则需要把VoodooI2C.kext和VoodooI2CHID.kext放入 L / E目录
    PS ：（10.14以下版本请自行测试）
## 硬件信息

```  
- CPU：Intel Core i7-5600U 2.6GHz (Boots 3.2GHz)

- 核心显卡：Intel HD 5500 Graphics 

- 声卡：ALC292

- 无线网卡：DW1820A CN-08PKF4 CN-0VW3T3 CN-00JT494（感谢 @Axelpop ）
```

## BIOS (1.37)
-  Security -> Security Chip`: **Disabled**;
-  Memory Protection -> Execution Prevention`: **Enabled**;
-  Virtualization -> Intel Virtualization Technology`: **Enabled**;
-  Internal Device Access -> Bottom Cover Tamper Detection`: must be **Disabled**;
-  Anti-Theft -> Current Setting`: **Disabled**;
-  Anti-Theft -> Computrace -> Current Setting`: **Disabled**;
-  Secure Boot -> Secure Boot`: **Disabled**;
-  UEFI/Legacy Boot`: **UEFI Only**;
-  CSM Support`: **Yes**.

## 有效

- 睡眠/唤醒
- Wifi
- 蓝牙 
- Handoff, Continuity, AirDrop
- iMessage, FaceTime, App Store, iTunes Store
- 以太网卡
- 板载音频 (使用alc_fix和CodecCommander.kext修复音频问题)
- USB
- 电池
- 触摸屏 （10.15需要使用VoodooI2C.kext和VoodooI2CHID.kext）
- 触摸板 （如果出现问题请把VoodooPS2Controller.kext放入 L / E 目录）
- 小红点
- miniDP
- SD卡读卡器

## 无效

- VGA
