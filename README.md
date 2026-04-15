# Arch Linux NVIDIA Quick Install

In this version, I have set up a common installation script that will install the NVIDIA GPU drivers of your choice (based on the version you pick).

> [!IMPORTANT]
> **1.** You must have **yay** or **paru** installed, as this guide is specifically for Arch and Arch-based distributions.
> 
> **2.** Make sure you have linux-headers (or linux-zen-headers, etc.) installed for your current kernel before running the script.

## Requirements

If you don't have an AUR helper, install one of them:

**To install yay:**
```bash
sudo pacman -S --needed base-devel git && git clone https://archlinux.org && cd yay && makepkg -si
```
**To install paru:**
```bash
sudo pacman -S --needed base-devel git && git clone https://archlinux.org && cd paru && makepkg -si
```


## Quick Start

### 1. **Download the script:**
```bash
curl -L -O 'https://github.com/ha1ron23/bash-script-to-install-nvidia-GPU-drivers/releases/download/NVIDIA-V2/nvidia_install.sh'
```

### 2. Run the installer
```bash
chmod +x nvidia_install.sh
./nvidia_install.sh
```

### How it works
The script automates the installation of two core packages from AUR:

    nvidia-[version]xx-utils
    nvidia-[version]xx-dkms

When prompted, simply enter the version number you need (e.g., 550, 560, or 580)
  
### Verification
After the installation finishes, the script will automatically run:
```bash
nvidia-smi
```
If you see the GPU status table, your drivers are correctly installed and recognized

### Uninstallation
To remove the drivers installed by this script, use:
```bash
sudo pacman -Rs nvidia-[your_version]xx-utils nvidia-[your_version]xx-dkms
```

## License
This project is licensed under the **MIT License**. You are free to use, modify, and distribute it.
