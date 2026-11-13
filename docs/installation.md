# Installation guide

This guide explains how to download, verify, install, update and uninstall HexaDesktop on every supported platform.

- [Windows](#windows)
- [macOS](#macos)
- [Linux](#linux)
- [Verifying your download](#verifying-your-download)
- [Updating](#updating)
- [Uninstalling](#uninstalling)

---

## Windows

**Requirements:** Windows 10 or 11, 64-bit.

### Installer (recommended)

1. Go to the [latest release](https://github.com/gethexa/HexaDesktop-Releases/releases/latest) and download `HexaDesktop-Setup-<version>-x64.exe`.
2. Double-click the downloaded file.
3. If Windows SmartScreen shows *"Windows protected your PC"*, make sure the publisher is **Hexa**, then click **More info → Run anyway**.
4. Follow the setup wizard. By default HexaDesktop installs to `%LOCALAPPDATA%\Programs\HexaDesktop` and does not require administrator rights.
5. Launch HexaDesktop from the Start menu or the desktop shortcut.

### Portable version

1. Download `HexaDesktop-<version>-win-x64.zip`.
2. Right-click the file → **Extract All…** and choose a folder (for example a USB drive).
3. Run `HexaDesktop.exe` from the extracted folder.

> [!NOTE]
> The portable version does not update automatically. Download the new `.zip` to upgrade.

### Silent install (IT administrators)

```powershell
HexaDesktop-Setup-<version>-x64.exe /S
```

---

## macOS

**Requirements:** macOS 12 (Monterey) or later.

1. Download the `.dmg` for your Mac:
   - **Apple Silicon** (M1 and newer): `HexaDesktop-<version>-arm64.dmg`
   - **Intel**: `HexaDesktop-<version>-x64.dmg`
2. Open the `.dmg` file.
3. Drag **HexaDesktop** into the **Applications** folder.
4. Eject the disk image.
5. Open HexaDesktop from **Applications** or Launchpad.

If macOS says the app *"can't be opened because it is from an unidentified developer"*, open **System Settings → Privacy & Security**, scroll down and click **Open Anyway**.

---

## Linux

**Requirements:** a 64-bit distribution from 2020 or later (Ubuntu 20.04+, Debian 11+, Fedora 36+ or equivalent).

### AppImage (any distribution)

```bash
chmod +x HexaDesktop-<version>-x86_64.AppImage
./HexaDesktop-<version>-x86_64.AppImage
```

If the AppImage does not start, install FUSE 2 (for example `sudo apt install libfuse2` on Ubuntu 22.04+).

### Debian / Ubuntu (.deb)

```bash
sudo apt install ./hexadesktop_<version>_amd64.deb
```

Then launch **HexaDesktop** from your applications menu or run `hexadesktop` in a terminal.

---

## Verifying your download

Every release includes a `SHA256SUMS.txt` file. Compare the checksum of your file with the one listed there.

**Windows (PowerShell)**

```powershell
Get-FileHash .\HexaDesktop-Setup-<version>-x64.exe -Algorithm SHA256
```

**macOS**

```bash
shasum -a 256 HexaDesktop-<version>-arm64.dmg
```

**Linux**

```bash
sha256sum -c SHA256SUMS.txt --ignore-missing
```

If the values do not match, delete the file and download it again. If they still don't match, [report it to us](../SECURITY.md).

---

## Updating

HexaDesktop checks for updates automatically when it starts. When a new version is available you'll see a notification — click **Restart to update**.

To check manually, open **Help → Check for updates** (on macOS: **HexaDesktop → Check for updates**).

The portable Windows build and the Linux `.deb` package do not update automatically: download the new version from the [Releases page](https://github.com/gethexa/HexaDesktop-Releases/releases/latest) and install it over the old one. Your settings and data are kept.

---

## Uninstalling

| Platform | How to uninstall |
| --- | --- |
| **Windows** | **Settings → Apps → Installed apps → HexaDesktop → Uninstall** |
| **macOS** | Drag **HexaDesktop** from **Applications** to the Trash |
| **Linux (.deb)** | `sudo apt remove hexadesktop` |
| **Linux (AppImage)** | Delete the `.AppImage` file |

Uninstalling keeps your local settings in case you reinstall. To remove them too, delete this folder:

| Platform | Settings folder |
| --- | --- |
| Windows | `%APPDATA%\HexaDesktop` |
| macOS | `~/Library/Application Support/HexaDesktop` |
| Linux | `~/.config/HexaDesktop` |
