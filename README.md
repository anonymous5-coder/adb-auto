# adb-auto

One-time No-WiFi auto-ADB setup via Termux (one-time Wi-Fi only).

Automates wireless debugging pairing, port detection, and persistent `localhost:5555` connection. After the initial setup, you can turn Wi-Fi off and use ADB over mobile data until the next reboot.

## Features

- Auto-detects pairing and connection ports via mDNS (Zeroconf)
- Notification-based pairing code entry (no terminal switching)
- Persistent `localhost:5555` connection via `adb tcpip`
- Helper commands: `start`, `reconnect`, `disconnect`, `status`, `reset`, `help`

## Installation

Add the APT repository and install the package:

~~~bash
echo "deb [trusted=yes] https://anonymous5-coder.github.io/adb-auto/ termux main" > $PREFIX/etc/apt/sources.list.d/adb-auto.list
pkg update
pkg install adb-auto
~~~

## Usage

~~~bash
adb_auto start       # Full setup: pair, connect, persist
adb_auto reconnect   # One-line reconnect to localhost:5555
adb_auto disconnect  # Disconnect from localhost:5555
adb_auto status      # Show connected devices
adb_auto reset       # Clear cache and kill ADB server
adb_auto help        # Show all commands
~~~

## Requirements

- Termux with `android-tools`, `python`, and `termux-api` installed
- Termux:API app installed on the device
- Wireless Debugging enabled in Developer Options
- `pip install zeroconf` (installed automatically on first run)

## License

MIT
