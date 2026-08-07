# OpenCore EFI for HP 14s-fq1092AU

OpenCore EFI configuration for the HP 14s-fq1092AU laptop.

This EFI was initially generated using OpenCoreSimplify and subsequently modified and customized.

---

## Hardware Specifications

- **Laptop Model**: HP 14s-fq1092AU
- **Processor**: AMD Ryzen 5 5500U (6 Cores / 12 Threads)
- **Graphics**: AMD Radeon Graphics (Integrated iGPU)
- **SMBIOS**: MacBookPro16,2

---

## Hardware Status Summary

| Feature | Status | Details / Kexts |
| :--- | :---: | :--- |
| **Graphics Acceleration & HiDPI** | Working | AMD Radeon Graphics & HiDPI scaling via NootedRed.kext |
| **Keyboard & Brightness Keys** | Working | via VoodooPS2Controller.kext & BrightnessKeys.kext |
| **Trackpad / Touchpad** | Working | via VoodooI2C.kext & VoodooI2CHID.kext |
| **Camera** | Working | Built-in webcam working |
| **Battery Indicator & Status** | Working | via SMCBatteryManager.kext |
| **NVMe & Storage** | Working | via NVMeFix.kext |
| **USB Ports** | Working | via USBToolBox.kext & UTBDefault.kext |
| **Wi-Fi & USB Tethering** | Working | via rtw88.kext & HoRNDIS.kext |
| **Power Management & Sensors** | Working | via VirtualSMC, SMCProcessor, SMCRadeonSensors |
| **Sound / Audio** | Partially Working | Earphones work; internal speakers do not work |
| **Microphone** | Not Tested | Internal microphone do not work, external mic status is currently untested |
| **Bluetooth** | Not Working | Bluetooth interface is not working |

Note: Internal speakers and Bluetooth are not working. Earphones and Camera work properly. Microphone is untested. Please check and adjust the EFI configuration as per your requirements.

---

## HiDPI Configuration

- **Display & Graphics Driver**: HiDPI scaling and hardware graphics acceleration are driven by `NootedRed.kext` for the AMD Ryzen 5 5500U iGPU.
- **Boot Picker Resolution**: `UIScale` is set to `0` (Auto) under `UEFI -> Output` in `config.plist` for automatic HiDPI scaling in the OpenCore boot menu.

---

## Setup Checklist & Credits

1. **SMBIOS Credentials**:
   - Use [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) to generate your own `SystemSerialNumber`, `SystemUUID`, and `MLB` for `MacBookPro16,2`.
   - Update `OC/config.plist` under `PlatformInfo -> Generic`.

2. **Credits & Custom Adjustments**:
   - Built with OpenCoreSimplify and modified later.
   - Wi-Fi support for Realtek RTL8822CE was made working with help from [thegwchr/Feixiao](https://github.com/thegwchr/Feixiao).

---

## EFI Structure

```text
EFI/
├── BOOT/
│   └── BOOTx64.efi
├── Microsoft/
└── OC/
    ├── ACPI/
    ├── Drivers/
    ├── Kexts/
    ├── Resources/
    ├── Tools/
    └── config.plist
```
