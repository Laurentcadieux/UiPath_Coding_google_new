# UiPath_Coding_google_new

## Overview

This UiPath Windows project contains a modern XAML workflow that opens Chrome to Google, searches for `UiPath news`, extracts the first three Google result titles, and displays those titles in a message box.

The main workflow file is `Main.xaml`.

## Project Details

- Project name: `UiPath_Coding_google_new`
- Target framework: `Windows`
- Expression language: `VisualBasic`
- Main entry point: `Main.xaml`
- Primary automation style: Modern UiPath UI Automation

## Dependencies

The project uses these UiPath packages:

- `UiPath.System.Activities` version `[24.10.7]`
- `UiPath.UIAutomation.Activities` version `[25.10.4]`

## Workflow Behavior

The workflow performs these steps:

1. Starts from the `Main Sequence`.
2. Declares three string variables:
   - `title1`
   - `title2`
   - `title3`
3. Opens or attaches to Chrome through a modern `Use Application/Browser` activity.
4. Navigates to `https://www.google.com`.
5. Types `UiPath news` into the Google search box and submits the search.
6. Reads the text of the first three search result titles.
7. Shows the extracted titles in a message box titled `Top 3 UiPath News Results`.

## Important Studio Setup Step

The UI Automation targets are intentionally marked with `TODO Indicate` in `Main.xaml`. Open the project in UiPath Studio and indicate the following elements before running the process:

- Chrome browser application/card target
- Google search input box
- First search result title
- Second search result title
- Third search result title

After indication, Studio will populate the real UI selectors/Object Repository references for your machine and browser.

## Files

- `project.json` - UiPath project metadata, dependencies, runtime options, and entry point configuration.
- `Main.xaml` - Main automation workflow.
- `.gitignore` - Excludes generated UiPath runtime files, build output, logs, and local editor files.
- `read.md` - Documentation for this project.

## How to Run

After indicating the UI targets in Studio, run the workflow with:

```powershell
C:\Users\laurent.cadieux\AppData\Roaming\npm\uip.cmd rpa run --file-path C:\Users\laurent.cadieux\Documents\UiPath\UiPath_Coding_google_new\Main.xaml --output json
```

You can also run it directly from UiPath Studio by opening the project folder and running `Main.xaml`.

## Validation Notes

During creation, local XML parsing confirmed that `Main.xaml` is well formed and `project.json` parses correctly.

The UiPath CLI validation and build commands could not complete in this environment because the machine has .NET runtimes but no .NET SDK installed. The UiPath headless Studio runtime requires the SDK to restore Helm packages.

Install a compatible .NET SDK, then validate with:

```powershell
C:\Users\laurent.cadieux\AppData\Roaming\npm\uip.cmd rpa validate --file-path Main.xaml --project-dir C:\Users\laurent.cadieux\Documents\UiPath\UiPath_Coding_google_new --output json
C:\Users\laurent.cadieux\AppData\Roaming\npm\uip.cmd rpa build C:\Users\laurent.cadieux\Documents\UiPath\UiPath_Coding_google_new --output json
```

## Git Setup

This folder includes a `.gitignore` suitable for a UiPath project. To initialize Git from this folder:

```powershell
cd C:\Users\laurent.cadieux\Documents\UiPath\UiPath_Coding_google_new
git init
git add .
git commit -m "Initial UiPath Google news workflow"
```
