# ACID — Andrew's Calcium Imaging Decoder

ACID is a desktop application for processing and analysing calcium imaging data. It is designed for researchers working with fluorescence recordings from multiple cells across multiple experimental conditions.

## Features

- Load one or more CSV or LOG data files
- Automatically detect and skip metadata rows, with manual correction available
- Correct for reversed time ordering in files where data runs in descending order, assuming time is in the first column
- Select and configure which columns represent cells and which represents the background reference
- The background column must be in the same position across all files
- Background-subtract fluorescence values row by row across all active cell columns
- Align data start rows across files, with per-file confirmation
- Group files into experimental conditions for averaged traces
- Interactive graph with draggable window bounds, per-series value readout, and discrete time snapping
- Window statistics including min, max, and standard deviation per group
- Welch's two-tailed t-test comparing group minimums or maximums against a user-selected control
- Export statistics and t-test results to CSV
- Save publication-ready graph images

## Installation

Go to the [Releases](../../releases) page and download the installer for your operating system.

### macOS
Download the `.dmg` file for your Mac:
- **Apple Silicon (M1/M2/M3):** download the `aarch64` `.dmg`
- **Intel Mac:** download the `x86_64` `.dmg`

Open the `.dmg`, drag ACID to your Applications folder, and launch it from there.

> **Note:** On first launch macOS may say the app is from an unidentified developer. If so, go to **System Settings → Privacy & Security** and click **Open Anyway**.

### Windows
Download the `.exe` or `.msi` installer, run it, and follow the prompts.

> **Note:** Windows may show a SmartScreen warning on first run. Click **More info → Run anyway**.

### Linux
Download the `.AppImage` file, make it executable, and run it:

```bash
chmod +x ACID_*.AppImage
./ACID_*.AppImage
```

Alternatively, download the `.deb` package and install it with:

```bash
sudo dpkg -i ACID_*.deb
```

## License

CC BY-NC 4.0 — free for academic and non-commercial use. See [LICENSE](LICENSE) for details.
