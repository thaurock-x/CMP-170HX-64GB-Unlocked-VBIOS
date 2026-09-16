<div align="center">
  <h1>✨️ NVIDIA CMP 170HX 64GB Unlocked VBIOS</h1>

[![VRAM Capacity](https://img.shields.io/badge/VRAM-64GB_HBM2e-brightgreen.svg)](#)
[![Device ID](https://img.shields.io/badge/Device_ID-0x20C2-blue.svg)](#)
[![Status](https://img.shields.io/badge/Status-Tested_%26_Verified-purple.svg)](#)

First public standalone 64GB HBM2e VBIOS dump (Device ID: `10DE 20C2`) for NVIDIA CMP 170HX accelerator cards. Unlocks full memory capacity for AI inference, local LLM execution, and compute workloads on both Windows and Linux.

------

## 📌 Overview

Standard public VBIOS files for device `0x20C2` often restrict card memory to 16GB. This repository contains the raw 1020 KB (1 MB) ROM dump extracted directly from an unlocked CMP 170HX card, enabling the full 64GB HBM2e VRAM capacity across multi-GPU compute rigs.

------

## ⚙️ Specifications & ROM Information

| Parameter | Specification |
| :--- | :--- |
| GPU Architecture | Ampere (GA100-based) |
| Device ID | `10DE 20C2` |
| Subsystem ID | `10DE 1585` |
| VRAM Capacity | 64 GB HBM2e (Unlocked) |
| VBIOS Version | `92.00.67.00.01` |
| Build Date | 05/12/21 (Modified 05/14/21) |
| EEPROM Size | 1020 KB (1 MB) |

------

## 🚀 How to Flash

🔹 Option A: Windows (Command Prompt as Administrator)
1. Download `nvflash64.exe` (v5.867.0 or newer).
2. Open CMD as Administrator and run:
   ```cmd
   nvflash64.exe -6 cmp170hx64gb_unlocked.rom

 • Press Y when prompted to confirm flashing across all matched device IDs.
 • Reboot the system.
🔹 Option B: Linux (Live USB / Driver Unloaded)
 • Boot into system without loading the NVIDIA kernel driver (or unload via sudo rmmod nvidia_uvm nvidia).
 • Flash using nvflash:
   sudo ./nvflash --protectoff
sudo ./nvflash -6 cmp170hx64gb_unlocked.rom

 • Reboot the system.

## 🔍 Verification
Run nvidia-smi to verify full 64GB detection:

+-----------------------------------------------------------------------------+
| NVIDIA-SMI 535.129.03             Driver Version: 535.129.03               |
|-------------------------------+----------------------+----------------------+
| GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|===============================+======================+======================|
|   0  Graphics Device     Off  | 00000000:08:00.0 Off |                  N/A |
| N/A   34C    P0    28W / 250W |      0MiB / 65536MiB |      0%      Default |
+-------------------------------+----------------------+----------------------+

---

### 💎 Reading EEPROM (this operation may take up to 30 seconds):
```text
Build GUID=23DEFEB5432341BD8EFE06C3A1596346

Build Number=29953139

IFR Subsysten ID=10DE-1585

Subsystem Vendor ID=Ox10DE

Subsystem ID=0x1585

Version=92.00.67.00.01

Image Hash=N/A

Hierarchy ID=Normal Board

Build Date=05/12/21

Modification Date=05/14/21

UEFI Version=No Version Found or Out-dated ()

UEFI Variant ID=A No Variant ID Found (No Variant ID Found)

UEFI Signer(s)=Unknown signer

XUSB-FW Version ID=N/A

XUSB-FW Build Time=N/A

InfoROM Version=1001.0108.01.02

InfoROM Backup=Present

License Placeholder=Present

GPU Mode=N/A

CEC OTA-signed Blob=Not Present
```

## 👤 Author & Acknowledgments
 • Dump & Testing: Thaurock
 • Special thanks: The open-source hardware, AI inference, and LLM self-hosting community.

---

### ​📄 Licencia:

<div align="center">
Desarrollado con 💚 por <strong>Thaurock</strong>
</div>
