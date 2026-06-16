# Windows VM Build

## Objective
Set up a fully functioning Windows 11 virtual machine for:

- PowerShell practice
- Windows administration
- Active Directory labs
- Microsoft 365 learning
- Azure learning
- Networking labs
- Security testing and experimentation

## Environment

### Host System

- Lenovo ThinkPad P16s Gen 4
- Windows 11 Pro
- Oracle VirtualBox

### Guest System

- Windows 11 Pro
- 8 GB RAM
- 4 vCPU
- 80 GB Virtual Disk
- NAT Networking
- TPM Enabled
- Secure Boot Enabled
- EFI Enabled
- VBoxSVGA Graphics Controller
- 128 MB Video Memory

## Installation Process

- Created Windows 11 virtual machine
- Allocated CPU, RAM and storage resources
- Enabled TPM, Secure Boot and EFI
- Mounted Windows 11 ISO
- Installed Windows 11 Pro
- Completed initial Windows setup
- Installed Windows updates
- Configured VirtualBox display settings

## Major Challenges Encountered

During deployment and configuration several issues were identified and investigated:

1. Initial VM boot failure caused by installation media and boot configuration issues.
2. Windows display scaling did not behave correctly within the VirtualBox window.
3. Windows boot process intermittently resulted in a black screen after the VirtualBox splash screen.
4. Graphics controller compatibility required investigation and testing.
5. Guest Additions installation required manual mounting and installation.
6. VM became unresponsive during Guest Additions reboot and required recovery actions.

Detailed investigations, evidence collection, root cause analysis and resolutions are documented in:

[Troubleshooting Log](troubleshooting.md)

## Key Learnings
- Windows 11 requires additional virtual hardware features such as TPM, Secure Boot and EFI.
- Guest operating systems can behave differently even when running on the same VirtualBox host.
- Display configuration issues can prevent an operating system from appearing to boot correctly.
- Screenshots and documented evidence are more reliable than memory when troubleshooting.
- Comparing a working system against a failing system is an effective troubleshooting technique.
- Systematic testing of one setting at a time helps isolate root causes.

## Final State

- Windows 11 installed successfully
- TPM 2.0 enabled
- Secure Boot enabled
- EFI enabled
- Windows updates installed
- Network connectivity functional
- Guest Additions installed
- Dynamic display resizing functional
- Display scaling configured for usability
- VM ready for future PowerShell, Active Directory, Azure and Windows administration labs

## Future Improvements

Planned enhancements for this virtual machine include:

- Configure PowerShell remoting and remote management features.
- Create snapshots prior to major configuration changes.
- Join the VM to a future Active Directory lab environment.
- Use the VM for Windows administration and troubleshooting exercises.
- Deploy Microsoft 365 and Azure management tools.
- Practice Windows networking and security configuration.
- Use the VM as a management workstation for future Azure and home lab projects.
- Document additional troubleshooting scenarios as they occur.

