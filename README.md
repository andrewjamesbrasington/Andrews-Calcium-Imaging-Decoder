# A Calcium Imaging Decoder (ACID)

![Build](https://github.com/andrewjamesbrasington/Andrews-Calcium-Imaging-Decoder/actions/workflows/build.yml/badge.svg)
![Release](https://img.shields.io/github/v/release/andrewjamesbrasington/Andrews-Calcium-Imaging-Decoder?include_prereleases)
![License](https://img.shields.io/badge/license-CC%20BY--NC%204.0-lightgrey)

ACID is a browser-based application for processing and analysing ratiometric calcium imaging data. It is designed for researchers working with fluorescence recordings produced by MetaFluor, and can be installed and run on most operating systems.

## Features

### Data loading and configuration
- Load one or more CSV or LOG files produced by MetaFluor
- Automatically detect and skip metadata rows, with manual correction available per file
- Detect and correct reversed time ordering where data runs in descending order
- Configure which columns represent cells; the background reference column defaults to the final column and can be reassigned by the user
- Toggle individual cell columns in or out of analysis, which applies across files
- Automatically background-subtract fluorescence values row by row across all active cell columns before data visualization and analysis

### Data Alignment and grouping
- Automatically detect data start rows across all loaded files, with per-file manual correction
- Assign files to named experimental groups for averaged traces and performing statistical tests
- Undo and redo grouping changes

### Data Visualisation
- Interactive canvas-based graph with draggable averaging-window bounds
- Per-series floating value readout at each bound handle
- Click-to-toggle legend for individual files and group averages
- Export graph images as PNG or SVG, with the filename used as the figure title

### Statistics and Analysis
- Compute min, max, and sample standard deviation per group within the averaging window
- **Two-sample Welch's t-test** (two-tailed, alpha = 0.05) when exactly two eligible groups are visible, comparing minimums or maximums against a user-selected control; reports Cohen's *d* with interpretation
- **Welch's one-way ANOVA** with Bonferroni post-hoc pairwise comparisons when three or more eligible groups are visible; reports ω² (omega-squared) as the omnibus effect size and Cohen's *d* for each selected comparison; Bonferroni correction uses only the comparisons selected by the user
- Export summary statistics and statistical test results to CSV as separate files

## Installation

Go to the [Releases](../../releases) page and download the installer for your operating system.

### macOS
Download the `.dmg` file for your Mac:
- **Apple Silicon (M1/M2/M3):** download the `aarch64` `.dmg`
- **Intel Mac:** download the `x86_64` `.dmg`

Open the `.dmg`, drag ACID to your Applications folder, and launch it from there.

> **Note:** On first launch macOS may say the app is from an unidentified developer. If so, go to **System Settings → Privacy & Security** and click **Open Anyway**. 
> - If this option is not available, copy and paste `xattr -cr /Applications/ACID.app` in the terminal, hit the enter key, then launch the app.

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
