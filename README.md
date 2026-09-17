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

&nbsp;
<p align="center">
  <img width="700" alt="RoboFile Fusion - Merge Screen" src="https://github.com/user-attachments/assets/b38a420c-d7c4-4593-b62d-30dba4d0db07" />
</p>
&nbsp;

* **Drag-and-Drop Drop Zone**: Drop any robot backup folder directly into the application, or use the standard folder browser.
* **Controller Brand Selector**: Choose your robot manufacturer (FANUC, Motoman, KUKA, ABB, Universal Robots, Kawasaki, Panasonic, Epson, or Generic) to automatically apply optimized file extension filters.
* **Automatic Output Management**: Automatically open and reveal the merged output file in Windows File Explorer upon completion.

&nbsp;
<p align="center">◈ ◈ ◈</p>
&nbsp;

### 2. Program Preview Screen
An interactive code inspection viewer for examining individual robot routines and full merged document previews before merging.

&nbsp;
<p align="center">
  <img width="700" alt="RoboFile Fusion - View Programs Screen" src="https://github.com/user-attachments/assets/e0d85827-d4b1-4796-a823-46816b3f0631" />
</p>
&nbsp;

* **Routine Dropdown & Step Navigation**: Switch seamlessly between individual routines or inspect the full merged output with Prev / Next step navigation buttons.
* **Live In-Code Search**: Filter program instructions in real-time matching your search query.
* **IDE & CLI Color Themes**: Switch between 5 selectable color schemes tailored for controls and robotics engineers:
  * **Light**
  * **Dark (IDE)**
  * **CLI Green**
  * **CLI Cyan**
  * **CLI Amber**
* **One-Click Clipboard Copying**: Instantly copy the routine or merged text directly to your clipboard.

&nbsp;
<p align="center">◈ ◈ ◈</p>
&nbsp;

### 3. Programs Library Screen
A comprehensive catalog view of all discovered robot routines before merging.

&nbsp;
<p align="center">
  <img width="700" alt="RoboFile Fusion - Programs Library Screen" src="https://github.com/user-attachments/assets/f5940f42-5c63-4f5f-93bf-a67e694f560a" />
</p>
&nbsp;

* **Selective Routine Inclusion**: Check or uncheck individual files to merge only the routines needed for your current audit.
* **Master Selection Toggle**: Quickly select or deselect all files with a single click.

&nbsp;
<p align="center">◈ ◈ ◈</p>
&nbsp;

### 4. Inputs & Outputs (I/O) Intelligence Table
An automated IO extraction engine that scans robot I/O signals and their associated comments.

&nbsp;
<p align="center">
  <img width="700" alt="RoboFile Fusion - Inputs &amp; Outputs Table" src="https://github.com/user-attachments/assets/c439c889-53ad-43a3-b68e-997e51b79842" />
</p>
&nbsp;

* **Automatic IO Extraction**: Automatically inspects checked routines to extract IO addresses, types, and logic occurrences.
* **Comment & Symbol Resolution**: Captures teach-pendant comments, descriptions, and user labels alongside signal addresses for fast verification.
* **Signal Type Filtering**: Filter instantly by Digital Inputs (`DI`), Digital Outputs (`DO`), Group I/O (`GI`/`GO`), Robot I/O (`RI`/`RO`), and Flags (`F`).
* **"With Comments Only" Filter**: Instantly isolate unused or empty addresses.
* **Export to CSV**: Export the resolved I/O table directly into `.csv` format for Microsoft Excel, PLC tag database mapping, or electrical commissioning binders.
* **Verification Status**: Tested and verified for the current build version of the application on **FANUC** (`.ls`, `.va`) and **Yaskawa Motoman** (`.jbi`) controllers.

&nbsp;
<p align="center">◈ ◈ ◈</p>
&nbsp;

### 5. Settings & Controller Presets Screen
Full control over target file extensions and ignored file patterns.

&nbsp;
<p align="center">
  <img width="700" alt="RoboFile Fusion - Settings Screen" src="https://github.com/user-attachments/assets/7844ca47-5952-484a-8c71-a560bdaea397" />
</p>
&nbsp;

* **Pre-Configured Controller Presets**: Ships with pre-configured settings for FANUC, KUKA, ABB, Yaskawa Motoman, Universal Robots, Kawasaki, Panasonic, and Epson.
* **Custom Target Extensions**: Define custom comma-separated file extensions to tailor scanning for proprietary or legacy robot formats.
* **Files to Ignore Filters**: Specify comma-separated wildcard patterns (e.g., `*.tp, *.log, *.bak`) to automatically exclude binary routines or temporary system logs.

&nbsp;
<p align="center">◈ ◈ ◈</p>
&nbsp;

### 6. About Screen
Application details, controller testing notices, and feedback channels.

&nbsp;
<p align="center">
  <img width="700" alt="RoboFile Fusion - About Screen" src="https://github.com/user-attachments/assets/a5accea3-ece9-4d25-859f-484f270ea5be" />
</p>
&nbsp;

* **App Details**: Version, build number, and application overview.
* **Verification & Testing Status**: Clarification of tested controllers (FANUC and Motoman for the current build) and implementation specifications.

&nbsp;
<p align="center">◈ ◈ ◈</p>
&nbsp;

## Supported Robot Formats

<div align="center">

| Manufacturer | Extensions | I/O Extraction Status |
| :--- | :--- | :--- |
| **FANUC** | `.ls`, `.va` | Verified (Current Build) |
| **Yaskawa Motoman** | `.jbi`, `.dat`, `.cnd` | Verified (Current Build) |
| **KUKA** | `.src`, `.dat`, `.sub` | Specification Implemented |
| **ABB** | `.mod`, `.prg`, `.sys` | Specification Implemented |
| **Universal Robots** | `.script`, `.txt` | Specification Implemented |
| **Kawasaki** | `.as`, `.pg` | Specification Implemented |
| **Panasonic** | `.prg`, `.dat` | Specification Implemented |
| **Epson** | `.prg`, `.pts` | Specification Implemented |
| **Generic** | `.txt` | Universal Text Merge |

</div>


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

1. Navigate to the Releases tab on the right side of this GitHub repository.
2. Download the latest **`RoboFile Fusion.exe`**.
3. Double-click **`RoboFile Fusion.exe`** to launch immediately.
4. **No installation required**: Runs standalone on Windows 10/11 (x64) without administrative privileges or separate runtime installers.

&nbsp;
<p align="center">◈ ◈ ◈</p>
&nbsp;

## Reporting Bugs & Routine Variations

* If you encounter routine parsing issues or syntax variations, please report them on the [GitHub Issues](https://github.com/arshdeepsingh404/RoboFile-Fusion/issues) page.
* Attaching sample backup directories or routine files helps diagnose controller syntax variations and expedite fixes.
