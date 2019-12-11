# Roadmap and TODOs

## Goal

As easily and as robustly as possible, convert a standard Windows system
to dual boot with Linux.
Linux configured the same as Windows with similar applications.

## Technology

This is subject to change over time.

* Runs from Windows
* No need for USB drive
* Post-install Linux script also written in Powershell
* YAML configured
* Windows Boot Manager (instead of grub)
* Powershell

## Roadmap

### PoC
* Limited Scripts to install Linux without any manual steps
* git clone install

### MVP - 0.1
* Set of individual PowerShell scripts.
* Opinionated, limited, non-robust
* Requires: Powershell 1.0, Win 10 64bit, Single OS(win), Single C:, EFI, no secure boot
* Installs: Dual boot, Linux Mint 64bit w/Cinnamon
* Configure basics: user account, locale, lang
* Install using DownloadString('github..ps1') | iex
* No support: XP/7/8, MBR, Bitlocker, AD, 32bit, LVM

### 0.2
* Run as exe as administrator (ps2exe)
* Port config: wifi passwords, locale, Chrome/Firefox settings
* Limited efi backup, restore, revert functionality.  before.cfg, after.cfg
* Bitlocker support
* Convert to GPT
* Reboot and continue without user intervention of password during install

### 1.0
* GUI
* Flexible.  Many entry-points and exit points.  Launch other utilities for help.
* Added support: Windows 7/8, MBR, flexible partitioning, 32 bit Windows
* Choice of several Debian/Ubuntu based distros
* Port settings and apps
* Plugins and flexible configuration to make it easy for others to help
* Buttons to go to web sites for help: google search, ubuntu support
* LVM and/or partition util?
* Programming Language change?
* Desktop icons: efi recover, OS in VM, reboot, browse files
* VirtualBox Linux host runs Windows partition w/sync protections.

## Other Possible Use Cases and sub-components
* Backup/Restore MBR/EFI
* Cleanup disk
* Shrink/Split/merge/move partitions
* Install Linux in a VM
* Convert Windows Partition to VM and delete
* Install existing Linux partition as VM
* Make Live USB
* Uninstall Linux dual boot
* Distro hop switcher
* Import settings/apps from Windows to Linux
* Import apps from Windows to OSS Windows
* Full convert from Windows to Linux
* EFI/Grub/boot menu recovery
* Remove Windows
* Install Windows after Linux

### Far Future
* Windows Vista/XP and 32bit support
* AD domain login
* Fully remove Windows with option to convert to VM
* Allow secure boot.  Detect if supportable.
* BIOS autoconfig. e.g. Dell client configuration utility
* BIOS help screens
* Minimal distro default if <=2GB.
* Non-debian distros.
* Distro switcher.  Add multiple distros into menu.
* Assist with backup
* Warnings/help for known problematic hardware
* MacOS to Elementary OS

## TODOs

### Development

#### Big Short-term Challenges
* EFI and boot menu
* Unattended Linux install in a VM
* Auto-Resume from reboot
* Help with backup/clone

#### Short Term
* Disable fast boot
* Disable Hyper-V
* Install powerwhell 1.0 if not available
* Install Virtualbox w/o choco (but use choco if's installed)

### Documentation
* Plugins how-to
* contribute.md
* support
* how to write a ticket: .log file

#### Contributing doc
* Work in branch
* Suggest: ticket first with "thumbs up" from me.
* Follow standards

#### standards
* .editorconfig
* lint check

### User Warnings and Errors

#### Checks

* Administrator
* enough space
* 64 bit
* Not on battery
* Virtualization enabled
* EFI/GPT/MBR, no secure boot
* Windows 10
* Powershell libs available
* Command line apps available
* Hyper V not enabled
* Choco installed
* Virtualbox installed
* Compatibility (some day)

#### Warnings

* Backup
* Upgrade firmware
* Disable secure boot
* Might brick your machine
* Limited support

#### Compatibility Warnings

* NVidia

## Support and Testing

### Manual Testing

* MBR vs EFI
* Test on Windows 7

### Automated Testing
* VirtualBox in VirtualBox. Nested VBox only supports 32bit OSes
* Download VMs from Microsoft
* Install apps in Windows
* Cache file downloads (option)
* Scenarios: MBR/EFI, Win 7/10
* Scripted.
* Limit phases.  Use snapshots for start phase.

## Impossible?
* Switch to/from MBR/GPT
* Disable secure boot
* Download and run c0firmware updater
* Enable virtualization

