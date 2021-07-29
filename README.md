# OpenCore 0.7.1 - Lenovo Ideapad 15IBD i3-5005 (No dGPU)

![About this Mac](.assets/images/Screenshot%202021-07-29%20at%2017.37.26.png)

## Specs

| Component      | Brand                                     |
|----------------|-------------------------------------------|
| **CPU**        | `Intel Core i3-5005U @ 2.0 GHz`           |
| **iGPU**       | `Intel HD Graphics 5500`                  |
| **Storage**    | `Western Digital Blue HD 1TB`  |
| **Audio Code** | `Conexant 20751`                |
| **Ethernet**  | `Realtek 8100`                |
| **OS**         | `macOS Big Sur 11.5.1 (20G80)`            |

### Working/Not working:

<details>
<summary>iGPU</summary>
  
- [x] Intel HD 5500 iGPU - Backlight support
- [x] Intel HD 5500 iGPU - HDMI Output
- [x] Intel HD 5500 iGPU - H264 & HEVC
</details>

<details>
<summary>Audio</summary>
  
- [x] Conexant 20751 - Internal Speakers
- [x] Conexant 20751 - Internal Microphone
- [x] Conexant 20751 - Combojack headphones
- [x] Conexant 20751 - HDMI Audio Output
</details>

<details>
<summary>USB</summary>
  
- [x] All USB ports working and mapped
- [ ] SD Card Reader (Not working)
- [x] Webcam (USB based)
</details>

<details>
<summary>Keyboard</summary>
  
- [x] Keyboard (PS2 based)
- [x] HID Key PWRB & SLPB 
</details>

<details>
<summary>Trackpad</summary>
  
- [x] PS2 Touchpad with gestures (Thanks to Acidanthera VoodooPS2)
</details>


<details>
<summary>Misc</summary>
  
- [x] Sleep/Wake using `hibernatemode` `0` 
- [x] Sensors CPU, iGPU, Battery, NVMe, Fans
- [x] Native NVRAM support
- [x] Recovery (macOS) boot from OpenCore
</details>

### Drivers

| Driver | Function |
| ---- | -------- |
| `HfsPlus or OpenHfsPlus` | Allow detecting and booting from HFS+ formatted partitions |
| `OpenRuntime` | Memory correction driver. Essential |

### Kexts

| Kext | Function |
| ---- | -------- |
| [AppleALC](https://github.com/acidanthera/AppleALC) | Native macOS HD audio for not officially supported codecs |
| [Lilu](https://github.com/acidanthera/Lilu) | Patching framework needed by most kexts |
| [ECEnabler](https://github.com/1Revenger1/ECEnabler) | Patching the Battery for battery status to work
| [USBInjectAll](https://bitbucket.org/RehabMan/os-x-usb-inject-all/downloads/) | Used for USB
| [RealtekRTL8100](https://github.com/Mieze/RealtekRTL8100) | Ethernet Driver
| [VirtualSMC](https://github.com/acidanthera/VirtualSMC) | Advanced SMC emulation |
| [VoodooPS2Controller](https://github.com/acidanthera/VoodooPS2) | Adds support for keyboard and touchpad|
| [WhateverGreen](https://github.com/acidanthera/WhateverGreen) | Various patches necessary for GPUs |

### SSDTs

| SSDT | Function |
| ---- | -------- |
| `SSDT-EC` | Used for disabling your real Embedded controller and creating a fake one for macOS to play with |
| `SSDT-HPET-DISABLE` | Used for disabling HPET device on macOS |
| `SSDT-PLUG` | Used for enabling Apple's XCPM in macOS, allowing for far better CPU power management |
| `SSDT-PNLF` | Used for controlling the backlight on internal display |

## Credits

* **Apple** for macOS
* [**Acidanthera**](https://github.com/acidanthera) for OpenCore and the majority of the kexts
* [**RehabMan**](https://github.com/RehabMan) for contributing to most of the ACPI patching guides I used
* [**Dreamwhite**](https://github.com/dreamwhite) for helping me with making the EFI (mostly SSDTs)