# Spoofer
Just a stupid spoofer made by me



# Steam & Anticheat Cleaner v2.0

A comprehensive C# WPF desktop application for cleaning Steam cache, registry traces, and removing anticheat artifacts. Advanced features include system restore points, process management, cloud sync cleaning, and more.

## ⚠️ DISCLAIMER

**This tool is for educational purposes only. Use at your own risk.**

- This tool **does NOT** and **will NOT** help you evade bans on gaming platforms
- This tool **does NOT** modify game files or cheat in any way
- This tool **only** removes log files, caches, and registry traces
- The author assumes no liability for any damage or data loss
- Always ensure you have backups before using system cleaning tools

---

## Features Overview

### Core Cleaning Categories

| Category | Description |
|----------|-------------|
| **Steam Traces** | App cache, logs, dumps, config files, registry entries |
| **Faceit AC** | %ProgramData%\FACEIT, %LocalAppData%\FACEIT, registry keys |
| **Riot Vanguard** | Logs, crash dumps, telemetry, registry markers (drivers preserved) |
| **Easy Anti-Cheat** | EAC logs, certificates, .dat files, registry entries |
| **BattlEye** | Logs, cache, game traces, registry entries |
| **Windows Traces** | Prefetch, temp files, thumbnail cache |

### Advanced Cleaning Features

| Feature | Description |
|---------|-------------|
| **Steam Cloud Sync Cleaner** | Clear sync conflicts, force cloud resync, clean temp files |
| **Download Cache Manager** | Clear depot cache, paused downloads, HTTP cache, workshop temps |
| **Workshop Content Cleaner** | Remove orphaned/unsubscribed workshop files |
| **Shader Cache Cleaner** | Clear Steam, DirectX, NVIDIA, AMD, Intel shader caches |
| **Event Logs Cleaner** | Clear Application/System logs with anticheat entries |
| **Network Traces Cleaner** | DNS cache flush, ARP clear, netsh reset, Winsock reset |
| **Recent Files Cleaner** | Recent items, jump lists, Explorer history, Run dialog |
| **Prefetch Analysis** | Identify and delete gaming-related prefetch files |
| **File Shredder** | 3-pass secure overwrite (DOD 5220.22-M standard) |

### System & Safety Features

| Feature | Description |
|---------|-------------|
| **System Restore Points** | Create Windows restore point before cleaning |
| **Process Manager** | Detect and kill conflicting Steam/anticheat processes |
| **Anticheat Status Detector** | Show active anticheats, drivers, services, processes |
| **Clean Verification** | Re-scan after cleaning to confirm traces removed |
| **Registry Backup** | Automatic .reg backup with restore capability |
| **Exclusion Manager** | Manage file/path exclusions with regex support |
| **Statistics Tracker** | Track cleaning sessions, files deleted, space freed |
| **Dry Run Mode** | Preview what would be deleted without changes |
| **MachineGuid Changer** | Change Windows MachineGuid (with backup) |

### Command-Line Mode

```bash
SteamCleaner.exe --help                           # Show help
SteamCleaner.exe --scan --steam                   # Scan only Steam traces
SteamCleaner.exe --clean --all --dry-run          # Full clean dry run
SteamCleaner.exe --full --silent                  # Silent full clean
SteamCleaner.exe --steam --eac --kill-processes --restore-point  # With safety features
```

---

## How to Use

### Basic Usage (GUI)

1. **Run as Administrator** - Right-click the EXE and select "Run as Administrator"

2. **Select Categories** - Check the cleaning categories you want to process:
   - Steam Traces
   - Faceit AC
   - Riot Vanguard
   - Easy Anti-Cheat
   - BattlEye
   - Windows Traces

3. **Configure Options** (Optional):
   - **Dry Run** - Preview only, no actual changes
   - **Create Restore Point** - Backup system before cleaning
   - **Kill Processes** - Auto-terminate conflicting processes
   - **Secure Shred** - 3-pass overwrite for sensitive files
   - **Change MachineGuid** - Modify Windows hardware ID

4. **Choose Action**:
   - **Scan** - Preview what would be found
   - **Clean** - Clean selected categories
   - **Full Clean** - Clean all categories at once

5. **Review Results** - Check the activity log for deleted items

### Advanced Features Usage

#### Process Manager
- Click **"Processes"** button to view running Steam/anticheat processes
- Shows process name, PID, window title, and path
- Kill individual processes or all conflicting at once

#### Exclusion Manager
- Click **"Exclusions"** button to manage exclusions
- Add file paths or registry keys to skip during cleaning
- Supports exact match, starts with, contains, pattern (regex)
- Load default game save exclusions to protect saves

#### Statistics Dashboard
- Click **"Stats"** button to view cleaning history
- Shows total sessions, files deleted, space freed
- Export reports and reset statistics

#### Backup Manager
- Click **"Backups"** button to view registry backups
- Restore previous registry values
- Delete old backups

#### Anticheat Status
The anticheat status is shown in logs when cleaning starts, displaying:
- Active/inactive state
- Running services
- Loaded drivers
- Running processes with PIDs

---

## Requirements

- Windows 10 or Windows 11 (64-bit)
- Administrator privileges (required for registry access)
- .NET 8.0 Runtime (included in self-contained EXE)

---

## Building from Source

### Prerequisites
- Visual Studio 2022 or later
- .NET 8.0 SDK

### Build Steps

1. Open `Spoofer.csproj` in Visual Studio or use command line:

```bash
cd "d:\vspreojects\Spoofer"

dotnet build -c Release


dotnet publish -c Release -r win-x64 --self-contained true /p:PublishSingleFile=true
```

2. The output will be in `bin\Release\net8.0-windows\` or the publish directory.

## Usage Guide

### First Launch

1. **Right-click** the executable and select "Run as Administrator"
2. The application will show "[Administrator]" in the title bar if elevated correctly
3. If not elevated, action buttons will be disabled and a warning is shown

### Scan Mode (Preview)

1. Check the categories you want to scan
2. Click **"Scan Only"**
3. Review the log to see what files and registry keys would be affected
4. Use this to understand what will be cleaned before making changes

### Clean Mode

1. Check the categories you want to clean
2. (Optional) Enable **"Dry Run Mode"** to preview without deleting
3. Click **"Clean Selected"**
4. Confirm the warning dialog
5. Watch the progress in the log output

### Full Clean

1. Click **"Full Clean"** to select and clean all categories
2. This performs the most comprehensive cleaning operation
3. **Warning:** This will clean ALL traces including all anticheat and Windows artifacts

### MachineGuid Change (Optional)

1. Check **"Change MachineGuid"** before cleaning
2. A backup of the original MachineGuid is automatically created
3. The MachineGuid will be changed to a new random GUID during cleaning
4. Use the Backup Manager to restore the original if needed

### Backup Manager

1. Click **"Backup Manager"** to view all registry backups
2. Select a backup and click **"Restore Selected"** to revert changes
3. Use **"Delete"** to remove old backup files

### Log Management

- Right-click the log area for context menu options:
  - **Copy** - Copy selected or all log text
  - **Clear Log** - Clear the log display
  - **Save Log...** - Open the log file location in Explorer

## What This Tool Does NOT Do

❌ **Does NOT** uninstall Steam or any games  
❌ **Does NOT** delete game save files (by default)  
❌ **Does NOT** remove or modify anticheat drivers (vgk.sys, EasyAntiCheat.sys, etc.)  
❌ **Does NOT** break Windows activation  
❌ **Does NOT** delete critical system files  
❌ **Does NOT** help you evade game bans  

## File Structure

```
SteamCleaner/
├── app.manifest                       # Admin elevation manifest
├── App.xaml/.cs                       # Application entry point with CLI support
├── MainWindow.xaml/.cs                # Main application window (GitHub dark theme)
├── BackupManagerWindow.xaml/.cs       # Registry backup manager
├── ExclusionManagerWindow.xaml/.cs  # Exclusion management
├── StatisticsWindow.xaml/.cs          # Statistics dashboard
├── ProcessManagerWindow.xaml/.cs      # Process manager
├── Models/
│   ├── CleanerCategory.cs             # Category model
│   └── BackupEntry.cs                 # Backup entry model
├── Services/
│   ├── AnticheatCleaner.cs            # Main cleaning logic
│   ├── RegistryBackup.cs              # Registry backup/restore
│   ├── Logger.cs                      # Logging service
│   ├── ProcessManager.cs              # Detect/kill processes
│   ├── SystemRestoreManager.cs        # Windows restore points
│   ├── EventLogCleaner.cs             # Windows Event Logs
│   ├── FileShredder.cs                # Secure file deletion
│   ├── NetworkTraceCleaner.cs         # DNS/ARP/network cleaning
│   ├── RecentFilesCleaner.cs          # Recent items/jump lists
│   ├── PrefetchAnalyzer.cs            # Prefetch analysis
│   ├── SteamCloudSyncCleaner.cs       # Steam cloud sync cleaning
│   ├── DownloadCacheManager.cs        # Steam download cache
│   ├── WorkshopCleaner.cs             # Orphaned workshop content
│   ├── ShaderCacheCleaner.cs          # GPU shader caches
│   ├── AnticheatStatusDetector.cs     # Status detection
│   ├── CleanVerification.cs           # Verification mode
│   ├── CommandLineParser.cs           # CLI argument parsing
│   ├── ExclusionManager.cs            # Exclusion management
│   └── StatisticsTracker.cs           # Statistics tracking
└── Utils/
    ├── AdminHelper.cs                 # Admin privilege check
    └── FileSystemHelper.cs            # Safe file operations
```

## Technical Details

### Registry Backup Format

Registry backups are stored as `.reg` files in the `Backups/` folder alongside a JSON index. These can be manually imported using `regedit.exe` if needed.

### Log Files

Logs are saved to `CleanLog_YYYYMMDD_HHMMSS.txt` in the application directory with full operation details.

### Async Operations

All cleaning operations run asynchronously with cancellation support to keep the UI responsive.

## Troubleshooting

### "Administrator Required" Warning

- Right-click the .exe and select "Run as Administrator"
- Or create a shortcut with "Run as administrator" enabled in Properties > Compatibility

### Some Files Could Not Be Deleted

- Files may be in use by running processes
- Close Steam and any games before cleaning
- Restart Windows if necessary and run cleaner before starting other applications

### Registry Restore Failed

- Ensure you are running as Administrator
- Check that the .reg backup file exists in the Backups folder
- Try importing the .reg file manually using regedit

## License

This software is provided as-is for educational purposes. The author is not responsible for any misuse or damage caused by this software.

## Changelog

### v2.0.0 - Major Update
- **New UI**: GitHub-style dark theme with rounded corners
- **Steam Cloud Sync Cleaner**: Clear sync conflicts, force resync
- **Download Cache Manager**: Clear depot cache, paused downloads, HTTP cache
- **Workshop Content Cleaner**: Remove orphaned/unsubscribed workshop files
- **Shader Cache Cleaner**: Clear Steam, DirectX, NVIDIA, AMD, Intel caches
- **Anticheat Status Detector**: Show active anticheats, drivers, services
- **Clean Verification Mode**: Re-scan to confirm traces removed
- **Process Manager**: Detect and kill conflicting processes
- **System Restore Points**: Create Windows restore points before cleaning
- **Event Logs Cleaner**: Clear anticheat-related Windows Event Logs
- **Network Traces Cleaner**: DNS flush, ARP clear, netsh reset
- **Recent Files Cleaner**: Clear jump lists, Explorer history, Run dialog
- **Prefetch Analysis**: Gaming prefetch identification and deletion
- **File Shredder**: 3-pass secure overwrite (DOD 5220.22-M)
- **Exclusion Manager**: Manage file/path exclusions with regex
- **Statistics Dashboard**: Track cleaning sessions and space freed
- **Command-Line Mode**: Full CLI support for automation

### v1.0.0
- Initial release
- Steam cache and registry cleaning
- Faceit AC, Vanguard, EAC, BattlEye trace removal
- Generic Windows trace cleaning (prefetch, temp, thumbnail cache)
- Registry backup and restore functionality
- Dry run mode for safe preview
- MachineGuid change capability

