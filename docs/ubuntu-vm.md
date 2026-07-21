# Ubuntu VM Build

## Objective
Set up a fully functioning Ubuntu Linux virtual machine for:

- Linux practice
- Security Lab foundations
- Networking foundations
- Cloud basics / learning

---

## Environment

### Host System

- Lenovo ThinkPad P16s Gen 4
- Windows 11 Pro
- Oracle VirtualBox

### Guest System

- Ubuntu 24.04 LTS
- 8 GB RAM
- 4 vCPU
- NAT Networking
- VMSVGA Graphics Controller
- 128 MB Video Memory
- 3D Acceleration Enabled

---

## Installation Process

- Installed VirtualBox
- Installed Extension Pack

- ISO Mounting
  - Downloaded Ubuntu ISO
  - Mounted ISO to VM
  - Booted from virtual optical drive

- Ubuntu Installation
  - Interactive install
  - Default apps selected
  - Wired connection
  - Created user account

---

## Major Challenges Encountered

During deployment and configuration several issues were identified and resolved:

1. Display rendering failure caused by an incompatible VirtualBox graphics configuration.
2. Guest display resizing was unavailable due to missing Guest Additions.
3. Guest Additions installation initially failed because required build dependencies were not installed.
4. Ubuntu became unresponsive during reboot following display configuration changes.
5. GRUB boot menu appeared after an interrupted reboot sequence.
6. systemd-journald experienced a watchdog timeout and journal corruption event after the host system entered sleep mode while the VM remained active.

Detailed investigations, evidence collection, root cause analysis and resolutions are documented in:

[Troubleshooting Log](troubleshooting.md).

---

## Key Learnings

- Virtual machine hardware settings directly affect operating system stability.
- Graphics controller selection can determine whether a VM boots correctly.
- Guest Additions provide drivers that improve host–guest integration.
- Guest Additions require kernel-specific headers and build dependencies.
- Linux package management is performed through APT repositories.
- Host system behaviour can impact guest operating systems.
- Linux services can be investigated using systemctl, crash reports and system logs.
- systemd-journald is responsible for collecting and storing Linux system logs.
- GRUB acts as the Linux bootloader and loads the operating system kernel.
- Troubleshooting is most effective when changing one variable at a time.
- Effective troubleshooting requires gathering evidence before making configuration changes.

---

## Final State

- Ubuntu VM fully working
- Screen resizing functional
- Guest Additions installed
- System updated

---

## Future Improvements

- Create and test VirtualBox snapshots
- Practice snapshot rollback and recovery
- Configure shared folders between host and guest
- Configure SSH access to the Ubuntu VM
- Build a Linux Hardening Lab on top of this environment