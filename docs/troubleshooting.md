# VirtualBox Linux and Windows VM's Troubleshooting

# Linux Ubuntu VM

## Issue 1: Display Rendering Failure

### Symptoms

- Black screen during boot
- VM failed to display Ubuntu desktop correctly

### Investigation

- Reviewed VirtualBox display configuration
- Compared settings against VirtualBox recommendations

### Root Cause

- Incompatible VirtualBox display configuration prevented rendering
  
### Resolution

- Changed Graphics Controller to VMSVGA
- Enabled 3D Acceleration

### Outcome

- Ubuntu booted successfully
- Display rendered correctly

---

## Issue 2: Guest Display Would Not Resize

### Symptoms

- Virtual machine window could be resized
- Ubuntu desktop resolution remained fixed and small

### Investigation

- Confirmed VirtualBox display settings were correct
- Determined Guest Additions were not installed

### Root Cause

- Missing Guest Additions drivers

### Resolution

- Installed VirtualBox Guest Additions

### Outcome

- Dynamic screen resizing became functional
- Improved integration between host and guest operating systems

---

## Issue 3: Guest Additions Installation Failed

### Symptoms

- Guest Additions installer failed during setup

### Investigation

- Reviewed installation output
- Identified missing build dependencies

### Root Cause

- Required kernel headers and build tools were not installed

### Resolution

```bash
sudo apt update
sudo apt install bzip2 build-essential dkms linux-headers-$(uname -r)
```

### Outcome

- Guest Additions installed successfully

---

## Issue 4: VM Freeze During Reboot

### Symptoms

- Ubuntu became unresponsive during reboot
- Boot process failed to complete

### Investigation

- Reviewed VirtualBox display configuration
- Tested alternative display settings

### Root Cause

- Display configuration conflict during restart

### Resolution

- Forced shutdown
- Restarted VM using corrected display settings

### Outcome

- System booted normally

---

## Issue 5: GRUB Boot Screen Appeared

### Symptoms

- GRUB bootloader menu appeared unexpectedly

### Investigation

- Verified system files and boot process

### Root Cause

- Interrupted reboot sequence

### Resolution

- Selected default boot option
- Continued normal startup

### Outcome

- Operating system loaded successfully

---

## Issue 6: systemd-journald Service Crash

### Symptoms

- Ubuntu displayed a "System Program Problem Detected" message
- Crash report generated in /var/crash
- No obvious loss of functionality after login

### Investigation

Commands used:

```bash
sudo systemctl --failed
ls -l /var/crash
sudo cat /var/crash/_usr_lib_systemd_systemd-journald.0.crash | less
systemctl status systemd-journald
last reboot
uptime
history
```

### Evidence discovered:

```text
systemd-journald.service: Watchdog timeout
systemd-journald.service: Killing process with signal SIGABRT
system.journal corrupted or uncleanly shut down
```

### Additional findings:

- systemd-journald had automatically restarted
- No failed services were present
- Journal file corruption was detected and repaired automatically

### Root Cause

Evidence suggests the crash occurred after the Lenovo host laptop entered sleep mode while the Ubuntu VM remained active.

The guest operating system was interrupted unexpectedly, resulting in journal corruption and a watchdog timeout.

### Resolution

- Investigated crash report
- Reviewed service status
- Confirmed automatic recovery
- Verified no additional failures existed

### Outcome

- systemd-journald restarted successfully
- Ubuntu remained stable
- No manual repair required

---

# Windows VM

## Issue 1: Initial VM Boot Failure

### Symptoms
- Virtual machine failed to boot successfully
- VirtualBox reported that no bootable device could be found
- Windows installation did not launch

### Investigation
- Verified virtual disk configuration
- Reviewed boot order configuration
- Confirmed installation media status

### Root Cause
- Windows installation media was not correctly configured during initial setup

### Resolution
- Mounted the Windows 11 ISO image
- Reconfigured the virtual machine installation process
- Restarted the VM using the correct installation media

### Outcome
- Windows installation launched successfully
- Operating system installation proceeded normally

---

## Issue 2: Windows Display Scaling and Resolution Problems

### Symptoms

- Windows desktop appeared blurry
- Text and icons were difficult to read
- Display scaling behaved inconsistently
- Virtual machine window resizing did not behave as expected

### Investigation

- Compared Windows VM behaviour against Ubuntu VM
- Reviewed VirtualBox display settings
- Verified video memory allocation
- Confirmed Guest Additions were not installed

### Root Cause

- VirtualBox Guest Additions were missing, preventing proper display integration between the host and guest operating systems.

### Resolution

- Mounted VirtualBox Guest Additions installation media
- Installed VBoxWindowsAdditions
- Rebooted the virtual machine
- Adjusted Windows display scaling to 200% for improved readability on the Dell monitor

### Outcome

- Display clarity improved significantly
- Dynamic display resizing became available
- Text and interface elements rendered correctly
- VM became comfortable to use for daily administration tasks

---

## Issue 3: Black Screen During Boot

### Symptoms

- Windows boot process occasionally stalled after the VirtualBox splash screen
- Desktop environment failed to appear
- System appeared unresponsive

### Investigation

- Compared behaviour with Ubuntu VM
- Reviewed VirtualBox graphics settings
- Tested alternative display configurations

### Root Cause

- Graphics controller compatibility and display configuration required investigation

### Resolution

- Tested display-related VirtualBox settings
- Documented observed behaviour
- Continued monitoring system stability

### Outcome

- System booted successfully
- Behaviour documented for future reference

---

## Issue 4: Guest Additions Installation

### Symptoms

- Automatic display resizing was unavailable
- Host and guest integration features were limited

### Investigation

- Mounted VirtualBox Guest Additions ISO
- Verified installation files were available within the guest operating system

### Root Cause

- VirtualBox Guest Additions had not yet been installed

### Resolution

- Mounted Guest Additions installation media
- Launched VBoxWindowsAdditions installer
- Completed installation wizard

### Outcome

- Guest Additions installed successfully
- Additional integration features became available

---

## Issue 5: VM Became Unresponsive During Guest Additions Reboot

### Symptoms

- Windows displayed "Restarting..."
- Reboot process did not complete
- VM appeared frozen for an extended period

### Investigation

- Monitored reboot process
- Verified Guest Additions installation had completed before restart
- Observed no further progress after several minutes

### Root Cause

- Guest operating system became unresponsive during reboot following Guest Additions installation

### Resolution

- Performed a virtual machine reset through VirtualBox
- Restarted the guest operating system

### Outcome

- Windows booted successfully
- Guest Additions remained installed
- System functionality was restored
