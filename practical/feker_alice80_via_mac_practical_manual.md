# FEKER Alice 80 – Practical VIA Configuration Manual (macOS)

## Purpose of This Document

This document records **only the steps and constraints that were actually required**
to configure the FEKER Alice 80 keyboard with VIA on macOS.

The following are intentionally NOT included:

- Recommended layouts
- Personal preferences
- Convenience tweaks or tuning

The goal is maximum reproducibility, based solely on verified behavior.

---

## Target Environment

- macOS
- FEKER Alice 80
- VIA (desktop application)

---

## macOS Prerequisites

### Function Key Behavior

On macOS, function keys may be intercepted by the OS.

Configure the following:

**System Settings → Keyboard → Keyboard Shortcuts → Function Keys**

- Enable: **Use F1, F2, etc. keys as standard function keys**

If this setting is not enabled:

- Keys such as F10 may never reach terminal applications
- VIA layer configuration may appear correct but does not work in practice

---

### Input Monitoring Permission

On macOS, some key events require **Input Monitoring** permission.

Check the following location:

**System Settings → Privacy & Security → Input Monitoring**

Allow input monitoring for:

- Terminal.app
- iTerm2.app
- Any terminal application you use

For TUI applications such as **Midnight Commander (mc)**,
some keys will not be detected without this permission.

---

## Why VIA Does Not Detect the Device Automatically

The FEKER Alice 80 is **not registered in VIA’s official device database**.

As a result:

- The keyboard is detected as a USB HID device
- VIA cannot associate it with a known keyboard definition
- VIA remains stuck at `Searching for device...`

This behavior is expected and not an error.

---

## Why VIA Stays at "Searching for device..."

Because the FEKER Alice 80 is **not present in VIA’s device database**:

- VIA can detect the device at the USB level
- However, it cannot understand the key layout, matrix, or layers
- **VIA cannot interpret the keyboard unless a JSON definition is loaded**

In this state:

- VIA remains in a waiting loop
- `Searching for device...` continues indefinitely

This is a design limitation of VIA, not a malfunction.

---

## If the Design Tab Is Not Visible

Depending on VIA settings, the **Design tab may be hidden**.

If the Design tab is not visible:

1. Launch VIA
2. Open the **Settings** tab
3. Enable **Show Design tab**
4. The Design tab will appear in the top bar

Without the Design tab, the VIA JSON file cannot be loaded.

---

## Required Procedure (Order Matters)

The following steps **must be performed in this order**.

1. Power off the keyboard
2. Connect the keyboard using a USB cable
3. Switch to wired mode by pressing **Fn + N**
4. Launch VIA
5. Open the **Design** tab
6. Manually load the official VIA JSON file

Unless the JSON file is loaded via the Design tab,
VIA will not recognize the keyboard.

---

## Fn Key and Layer Behavior

### Observed Behavior

The following behavior was confirmed:

- Standard VIA layer keys (e.g. `MO(1)`) do not work
- Fn key presses are not detected in VIA Key Tester
- The keyboard remains stuck on Layer 0

---

### Verified Working Assignment

Only the following assignment worked reliably:

- **Fn1(3)**

Observed behavior:

- VIA displays the key as `Fn1(3)`
- Assigning it enables correct layer switching
- VIA Key Tester confirms activation of Layer 1

This appears to be a **vendor-specific firmware implementation**
rather than standard VIA behavior.

---

## Terminal Application Example (Midnight Commander)

In terminal applications such as Midnight Commander:

- Before configuration:  
  - `Fn + 0` inputs `0`  
  - F10 does not work, preventing normal exit

- After assigning `Fn1(3)`:  
  - Layer switching functions correctly  
  - F10 is recognized as expected

---

## Saving Configuration

- VIA writes configuration directly to the keyboard
- No background process is required on macOS
- Settings persist across power cycles and reboots

---

## Returning to Wireless Mode

After configuration is complete:

1. Quit VIA
2. Disconnect the USB cable
3. Switch to Bluetooth or 2.4GHz wireless mode

The VIA configuration remains active in wireless mode.

---

## Notes

- Official VIA JSON files must be downloaded separately
- This repository does not redistribute official JSON files
- All information here is based on direct testing and observation
