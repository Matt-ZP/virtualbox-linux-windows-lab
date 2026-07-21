# VirtualBox Linux & Windows Lab

## Overview
In this lab I built and configured Ubuntu Linux and Windows 11 virtual machines using Oracle VirtualBox.

The purpose of the project was to:

- Learn virtualization fundamentals
- Create isolated environments for testing and experimentation
- Develop Linux administration skills
- Develop Windows administration skills
- Practice Linux CLI and PowerShell usage
- Develop troubleshooting and problem-solving skills

The lab included investigating and resolving issues involving VirtualBox graphics configuration, Guest Additions installation, and operating system stability. 

---

## Environment

## Host System

- Lenovo ThinkPad P16s Gen 4
- Windows 11 Pro
- Oracle VirtualBox

---

### Ubuntu VM

- Ubuntu 24.04 LTS
- 8 GB RAM
- 4 vCPU
- NAT Networking
- VMSVGA Graphics Controller
- 128 MB Video Memory
- 3D Acceleration Enabled (required to resolve display rendering issues)

---

### Windows 11 VM

- Windows 11 Pro
- 8 GB RAM
- 4 vCPU
- NAT Networking
- TPM Enabled
- Secure Boot Enabled
- EFI Enabled
- VBoxSVGA Graphics Controller
- 128 MB Video Memory

---

## Skills Demonstrated

- VM provisioning
- Resource allocation (CPU, RAM, storage)
- Virtual networking (NAT configuration)
- Operating system installation (Ubuntu Linux and Windows 11)
- Linux package management (APT)
- Linux CLI navigation
- PowerShell fundamentals
- VirtualBox Guest Additions installation
- Dependency troubleshooting (kernel headers, build tools, DKMS)
- Virtual graphics configuration
- Display rendering troubleshooting
- Windows boot troubleshooting
- Linux service investigation
- Log analysis using systemctl and journalctl
- Crash report analysis
- Root cause investigation
- System update management
- Virtual machine lifecycle management (start, stop, reboot)
- Technical documentation
- Structured troubleshooting methodology

---

## Key Learning Outcomes

- Understood how hypervisors abstract hardware resources for guest operating systems.
- Learned the relationship between host and guest operating systems.
- Gained experience troubleshooting graphics and display issues in VirtualBox.
- Learned why Guest Additions require kernel-specific build dependencies.
- Developed confidence using Linux and PowerShell command-line environments.
- Practiced investigating Linux service failures and system logs.
- Improved ability to isolate root causes through systematic testing.
- Learned the importance of documenting evidence rather than relying on memory during troubleshooting.

---

## Documentation

- [Ubuntu VM Build](docs/ubuntu-vm.md)
- [Windows VM Build](docs/windows-vm.md)
- [Troubleshooting Log](docs/troubleshooting.md)
- [Lessons Learned](docs/lessons-learned.md)