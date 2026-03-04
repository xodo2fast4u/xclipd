# xclipd

A native, instant and lightweight cross-platform clipboard manager developed by xodobyte.

## Features

- Instant clipboard monitoring with under 50ms latency
- System theme detection and automatic switching
- Global hotkey support for quick access
- System tray integration
- Configurable history limit
- Export history to text file
- Auto-paste to previously focused application
- Cross-platform support for Linux, Windows, and macOS

## Installation

### Pre-built Binaries

Download the latest release for your platform from the GitHub Releases page.

### Building from Source

#### Prerequisites

- Platform-specific dependencies (see below)

#### Linux Dependencies

```bash
sudo apt-get install libgtk-3-dev libxdo-dev
```

## Building

```basg
git clone https://github.com/xdobyte/xclipd.git
cd xclipd
cargo build --release
```

## Platform-specific Packaging
### Linux (Debian package)

```bash
cargo install cargo-deb
cargo deb
```
The package will be created in target/debian/.

### Windows (MSI installer)

```bash
cargo install cargo-wix
cargo wix
```
The installer will be created in target/wix/.

### macOS (App bundle)

```bash
cargo install cargo-bundle
cargo bundle --release
```
The app bundle will be created in target/release/bundle/.

## Configuration
The configuration file is stored in the platform-appropriate config directory:

- Linux: `~/.config/xclipd/config.toml`
- Windows: `%APPDATA%\xclipd\config.toml`
- macOS: `~/Library/Application Support/xclipd/config.toml`

## Configuration Schema

```bash
toml

[history]
limit = "Unlimited"

[appearance]
theme = "System"

[hotkey]
linux = "Super+V"
windows = "Win+V"
macos = "Cmd+Shift+V"
```

## History Limit
Set a positive integer to limit history entries, or use "Unlimited" (case-sensitive) for no limit.

## Theme Options
- System: Automatically follow system theme
- Light: Force light mode
- Dark: Force dark mode

## Global Hotkeys
Default hotkeys by platform:

- Linux: Super+V
- Windows: Win+V
- macOS: Cmd+Shift+V
Hotkeys can be rebound in the Settings panel.

## Usage
1. Launch xclipd
2. Copy text anywhere to add it to history
3. Press the global hotkey to open the clipboard manager
4. Click an entry to paste it into the previously focused application
5. Access settings via the system tray or toolbar

## System Tray
Right-click the system tray icon to access:

- Open xclipd
- Settings
- Clear History
- Quit

## Performance

- Clipboard monitoring: under 50ms latency
- UI rendering: 60fps or higher
- Memory usage: under 30MB with 500 items
- Cold startup: under 300ms

## License
MIT License

## Credits
Developed by xodobyte:
