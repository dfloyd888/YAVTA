# YAVTA
Yet another VT Appliance

-----

## Status

Right now, this is a pure concept.  The goal is a LCD screen connected to an embedded Linux controller that has one, possibly more, RS-232 serial ports, USB sockets for the keyboard, a plug for power, and nothing else.

The goal is simplicity and security.  This appliance does nothing more than provide a keyboard and mouse for a serial link.  It is not a laptop, nor (although this can change) do more than just be a HID for a console.

Features:

- An ARM CPU running an embedded Linux distribution like Wind River Linux or Wind River Pulsar Linux.  QNX is also a useful candidate, but the goal is to have the project completely open source (anything security related should be), and have the price be for the hardware.
- The device runs on a small flash drive (MicroSD card), and all it does is boot to the OS, and then handle keyboard and display input between the serial port and itself.
- The circuit board will be potted in epoxy.  This further ensures that it can't be physically tampered with, as well as help with extending the life of the components in the field.
- The keyboard will be the user's choice, and plug into a USB port that is configured only to allow only keyboards to work.  No mass storage, no NICs, only keyboards and nothing else.
- The terminal will have limited configuration settings.  At most, a menu to set the parity, terminal type, (VT52, VT100, ANSI), baud rate, and a screen blank timeout.
- The terminal will have an option for password protection with a single keystroke or idle timeout, as well as a button to completely disconnect and send a long break.  This way, one can be assured the terminal session is disconnected, although doing this on SPARC hardware will result in an "OK" prompt, halting the machine.  Keymapping will also be available, in case applications require items like F13-F15 keys.
- The terminal ideally will be able to handle oddball term types, such as hft, lft, 3270, and other items, with the ability to map keys.
- The terminal might  have an option for a parallel printer for "screenshots".  USB would be nice, but adding all the driver functionality would add potential security issues.
- The terminal will be able to have the usual colors, amber and black, with ANSI support if needed/wanted.
- A beefy locking connector, as well as a Kensington lock slot.

## Optional stuff

- Offering a SD card, so users could copy profiles (files with what color settings, password for unlocking, etc.)
- A USB port dedicated to printing, perhaps using a VM/hypervisor architecture, so if the little VM handling all the print drivers gets corrupted, it can't log keystrokes or display on the machine.
- A high security keylock.
- A S/PDIF or other fiber optic cable and two connectors.  This is intended to be wrapped around an object and plugged into the terminal, then a password set.  The terminal then sends random pulses through and validates what was sent.  This way, if the cable is broken or disconnected, the terminal will assume it is stolen, and inactivate itself, disabling any functionality until a password is inputted.
- A housing made from glass or ceramic so if the Kensington lock slot or other ones are destroyed, it is quite obvious.
- Bluetooth pairing with a dongle, so the device would auto-lock as soon as the wearer leaves.
- A Wi-Fi antenna that is used as a "watchdog", where the machine pings a central server.  If the SSID drops or the machine is unpingable, the terminal will shut down and demand a password before it can be used.  This is another way to mitigate theft.
- A built-in battery that functions not just as a UPS, but can power the machine for a number of hours, so it can be used for system recovery in case of a power failure (for example, if the router has power, but nothing else does.)
- A one piece housing for the screen and controller to further ensure tamper detection.
- A built in power supply which only charges the internal battery.  The components get their power from the battery.  This way, voltage fluctuations do not affect the terminal's output.
- Some type of voltage regulation on the USB and serial ports to mitigate USB killers.
- Some type of transponder to alert if the device detects tampering with.

## Purpose for the device.

The core purpose is to have a simple, secure "dumb" terminal.  Something that one doesn't have to worry about keystroke logging, screenshots being kept, and other access.

One goal is to have something that can be used in relatively hostile environments, be it humidity, dust, or extreme temperatures, as well as environments subject to security threats, like jails, prisons, receiving docks, or other places where theft or compromise is likely.