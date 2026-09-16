# RoboFile Fusion

**RoboFile Fusion** is a Windows desktop tool for merging multi-file industrial robot backups into a single text file and inspecting teach-pendant programs.

When working with robot backups (like FANUC All-of-Above backups or Motoman CF card dumps), cell routines are usually scattered across dozens or hundreds of individual files (`.ls`, `.jbi`, `.src`, `.mod`, etc.). During commissioning, troubleshooting interlocks, or mapping PLC I/O, tracking down used vs. spare signals and registers across all those files by hand takes a lot of time.

RoboFile Fusion solves this by scanning your backup folder and merging your selected routines into one searchable text document with clear program headers and an index. It also includes an in-app routine previewer with selectable color themes, and automatically pulls referenced I/O signals, comments, and flags into an interactive table that can be exported to CSV.

&nbsp;
<p align="center">◈ ◈ ◈</p>
&nbsp;

## Application Walkthrough & Features

### 1. Merge Programs Screen
The primary workstation for selecting backups, choosing controller specifications, and running the merge engine.

<p align="center">
  <img width="960" alt="RoboFile Fusion - Merge Screen" src="https://github.com/user-attachments/assets/b38a420c-d7c4-4593-b62d-30dba4d0db07" />
</p>

* **Drag-and-Drop Drop Zone**: Drop any robot backup folder directly into the application, or use the standard folder browser.
* **Controller Brand Selector**: Choose your robot manufacturer (FANUC, Motoman, KUKA, ABB, Universal Robots, Kawasaki, Panasonic, Epson, or Generic) to automatically apply optimized file extension filters.
* **Recursive Folder Scanning**: Toggle subdirectory recursion to scan nested directories or flatten multi-folder backup structures.
* **Non-Blocking Asynchronous Engine**: Merges hundreds of program files in seconds with a live progress bar, cancellation support, and non-freezing UI.
* **Automatic Output Management**: Option to automatically open and reveal the merged output file in Windows File Explorer upon completion.

&nbsp;
<p align="center">◈ ◈ ◈</p>
&nbsp;

### 2. Program Preview Screen
An interactive code inspection viewer for examining individual robot routines and full merged document previews before merging.

* **Routine Dropdown & Step Navigation**: Switch seamlessly between individual routines or inspect the full merged output with Prev / Next step navigation buttons.
* **Live In-Code Search**: Filter program instructions in real-time matching your search query, while preserving original robot file line numbers in the gutter.
* **IDE & CLI Color Themes**: Switch between 5 selectable color schemes tailored for controls and robotics engineers:
  * **Light**: Crisp daylight theme with high-contrast slate text.
  * **Dark (IDE)**: Dark code theme inspired by Visual Studio and VS Code.
  * **CLI Green**: Classic terminal / Matrix phosphor green aesthetic.
  * **CLI Cyan**: Deep navy and bright cyber cyan terminal styling.
  * **CLI Amber**: Retro monochrome CRT amber phosphor glow.
* **Synchronized Line Numbers Gutter**: Monospace line numbering synchronized across horizontal and vertical scrolling.
* **One-Click Clipboard Copying**: Instantly copy the routine or merged text directly to your clipboard.
* **File Metrics Badges**: Displays live line count and file size indicators for the inspected routine.

&nbsp;
<p align="center">◈ ◈ ◈</p>
&nbsp;

### 3. Programs Library Screen
A comprehensive catalog view of all discovered robot routines before merging.

<p align="center">
  <img width="960" alt="RoboFile Fusion - Programs Library Screen" src="https://github.com/user-attachments/assets/f5940f42-5c63-4f5f-93bf-a67e694f560a" />
</p>

* **Discovered Routine Catalog**: Inspect every detected routine with exact line counts, file size (in KB/MB), and last modified timestamp.
* **Selective Routine Inclusion**: Check or uncheck individual files to merge only the routines needed for your current audit.
* **Master Selection Toggle**: Quickly select or deselect all files with a single click.

&nbsp;
<p align="center">◈ ◈ ◈</p>
&nbsp;

### 4. Inputs & Outputs (I/O) Intelligence Table
An automated signal extraction engine that surfaces physical and internal robot I/O signals and their associated teach-pendant comments.

<p align="center">
  <img width="960" alt="RoboFile Fusion - Inputs &amp; Outputs Table" src="https://github.com/user-attachments/assets/c439c889-53ad-43a3-b68e-997e51b79842" />
</p>

* **Automatic Signal Extraction**: Automatically inspects checked routines to extract signal addresses, types, and logic occurrences.
* **Comment & Symbol Resolution**: Captures teach-pendant comments, descriptions, and user labels alongside signal addresses for fast verification.
* **Signal Type Filtering**: Filter instantly by Digital Inputs (`DI`), Digital Outputs (`DO`), Group I/O (`GI`/`GO`), Robot I/O (`RI`/`RO`), and Flags (`F`).
* **Live Search Query**: Filter signals in real-time by name, comment, address, or type.
* **"With Comments Only" Filter**: Instantly isolate documented signals from unused or empty addresses.
* **Summary Metric Cards**: Live counters displaying total signals, digital inputs, digital outputs, group signals, robot I/O, and flags.
* **Export to CSV**: Export the resolved I/O table directly into `.csv` format for Microsoft Excel, PLC tag database mapping, or electrical commissioning binders.
* **Verification Status**: Tested and verified for the current build version of the application on **FANUC** (`.ls`, `.va`) and **Yaskawa Motoman** (`.jbi`) controllers.

&nbsp;
<p align="center">◈ ◈ ◈</p>
&nbsp;

### 5. Settings & Controller Presets Screen
Full control over target file extensions and ignored file patterns.

<p align="center">
  <img width="960" alt="RoboFile Fusion - Settings Screen" src="https://github.com/user-attachments/assets/7844ca47-5952-484a-8c71-a560bdaea397" />
</p>

* **Pre-Configured Controller Presets**: Ships with pre-configured settings for FANUC, KUKA, ABB, Yaskawa Motoman, Universal Robots, Kawasaki, Panasonic, and Epson.
* **Custom Target Extensions**: Define custom comma-separated file extensions to tailor scanning for proprietary or legacy robot formats.
* **Files to Ignore Filters**: Specify comma-separated wildcard patterns (e.g., `*.tp, *.log, *.bak`) to automatically exclude binary routines or temporary system logs.
* **Persistent Settings**: User configurations automatically persist across application restarts in local storage.

&nbsp;
<p align="center">◈ ◈ ◈</p>
&nbsp;

### 6. About Screen
Application details, controller testing notices, and feedback channels.

<p align="center">
  <img width="960" alt="RoboFile Fusion - About Screen" src="https://github.com/user-attachments/assets/a5accea3-ece9-4d25-859f-484f270ea5be" />
</p>

* **App Details**: Version, build number, and application overview.
* **Verification & Testing Status**: Clarification of tested controllers (FANUC and Motoman for the current build) and implementation specifications.
* **Bug Reporting & Support**: Guidance on reporting routine syntax discrepancies and submitting sample files.
* **Repository Reference**: Reference link to the official project repository.

&nbsp;
<p align="center">◈ ◈ ◈</p>
&nbsp;

## Supported Robot Formats

| Manufacturer | Extensions | Language / Routine Types | I/O Extraction Status |
| :--- | :--- | :--- | :--- |
| **FANUC** | `.ls`, `.va` | ASCII Program Files & Variable Files | Verified (Current Build) |
| **Yaskawa Motoman** | `.jbi`, `.dat`, `.cnd` | INFORM Job Files, Data & Condition Files | Verified (Current Build) |
| **KUKA** | `.src`, `.dat`, `.sub` | KRL Source Routines, Data, Submit Interpreter | Specification Implemented |
| **ABB** | `.mod`, `.prg`, `.sys` | RAPID Modules & System Files | Specification Implemented |
| **Universal Robots** | `.script`, `.txt` | URScript Routines & Scripts | Specification Implemented |
| **Kawasaki** | `.as`, `.pg` | AS Language & Program Files | Specification Implemented |
| **Panasonic** | `.prg`, `.dat` | TAWERS Program & Data Files | Specification Implemented |
| **Epson** | `.prg`, `.pts` | SPEL+ Programs & Point Coordinate Files | Specification Implemented |
| **Generic** | `.txt` | Plain-text automation routines / custom code | Universal Text Merge |

&nbsp;
<p align="center">◈ ◈ ◈</p>
&nbsp;

## Non-Destructive File Safety Policy

RoboFile Fusion is built with strict safety guarantees to safeguard critical industrial backups:

* **Strict Read-Only Source Policy**: Original teach-pendant backup folders and routines are accessed in read-only mode. The application **never modifies, overwrites, or deletes** any source files.
* **User-Designated Destination**: Merged documents are written exclusively to a user-specified output path.
* **Standardized File Attribution**: Each merged file starts with a top-level attribution header, timestamp, controller specification, and a manifest index of all included programs. Each routine inside the document is demarcated with a clear separator and file details.

&nbsp;
<p align="center">◈ ◈ ◈</p>
&nbsp;

## Download & Run Instructions

RoboFile Fusion is distributed as a **portable single-file executable (`.exe`)**:

1. Download **`RoboFile Fusion.exe`** from the [GitHub Releases](https://github.com/arshdeepsingh404/RoboFile-Fusion/releases) page.
2. Double-click **`RoboFile Fusion.exe`** to launch immediately.
3. **No installation required**: Runs standalone on Windows 10/11 (x64) without administrative privileges or separate runtime installers.

&nbsp;
<p align="center">◈ ◈ ◈</p>
&nbsp;

## Reporting Bugs & Routine Variations

Due to syntax differences across robot software revisions, controller generations, and installed software options:
* If you encounter routine parsing issues or syntax variations, please report them on the [GitHub Issues](https://github.com/arshdeepsingh404/RoboFile-Fusion/issues) page.
* Attaching sample backup directories or routine files helps diagnose controller syntax variations and expedite fixes.

&nbsp;
<p align="center">◈ ◈ ◈</p>
&nbsp;
