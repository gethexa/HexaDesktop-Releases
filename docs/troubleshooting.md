# Troubleshooting

Try the fixes below before contacting support. Most problems are solved by **updating to the latest version** and **restarting the app**.

## Installation problems

### Windows: "Windows protected your PC"

This SmartScreen message can appear for new releases. Check that the publisher is **Hexa**, then click **More info → Run anyway**.

### macOS: "HexaDesktop can't be opened"

Open **System Settings → Privacy & Security**, scroll down and click **Open Anyway** next to the HexaDesktop message.

### macOS: "HexaDesktop is damaged and can't be opened"

The download was probably corrupted. Delete the app, [verify the checksum](installation.md#verifying-your-download) of a fresh download and install again.

### Linux: the AppImage doesn't start

Make sure it is executable (`chmod +x`) and that FUSE 2 is installed (`sudo apt install libfuse2`).

## Sign-in problems

- Make sure you can sign in to the Hexa web app with the same email and password.
- Check your computer's **date and time** are set automatically — a wrong clock breaks secure sign-in.
- If you use a corporate network, a proxy or firewall may block the connection. See **Settings → Advanced → Proxy**.

## The app won't start or shows a blank window

1. Quit HexaDesktop completely (including from the system tray / menu bar).
2. Start it again.
3. If the window is still blank, turn off **Settings → Advanced → Hardware acceleration**. If you can't reach settings, start the app with:
   - Windows: `HexaDesktop.exe --disable-gpu`
   - macOS: `open -a HexaDesktop --args --disable-gpu`
   - Linux: `hexadesktop --disable-gpu`
4. As a last resort, rename the [settings folder](installation.md#uninstalling) to reset the app to its defaults.

## Sync problems

- Look at the sync indicator in the status bar and click it for details.
- Check your internet connection.
- Sign out and sign back in.
- Use **Settings → Privacy → Clear local cache** to download a fresh copy of your data.

## The app is slow

- Update to the latest version.
- Close windows you aren't using.
- Clear the local cache (**Settings → Privacy → Clear local cache**).

## Collecting logs for support

Use **Help → Report a problem** to collect logs automatically. You can also find the log files here:

| Platform | Logs folder |
| --- | --- |
| Windows | `%APPDATA%\HexaDesktop\logs` |
| macOS | `~/Library/Logs/HexaDesktop` |
| Linux | `~/.config/HexaDesktop/logs` |

Attach the most recent log file to your [bug report](https://github.com/gethexa/HexaDesktop-Releases/issues/new?template=bug_report.yml). Logs do not contain your password, but please review them before posting publicly.

## Still stuck?

See [SUPPORT.md](../SUPPORT.md) for ways to contact us.
