---
title: Setup
---

This module uses two free tools:

- **Google Colab** for the Python notebooks in the Introduction episode. It runs in your web browser,
  so there is nothing to install.
- **QGIS** for the Getting Started with QGIS and Accessibility episodes. It is a desktop program you
  install once.

## What you need

- A Google account (for Colab)
- A computer where you can install software (for QGIS)
- Optional: a free [Census API key](https://api.census.gov/data/key_signup.html) for the optional
  Census section of notebook 1c. It arrives by email; click the activation link before using it.

## Part 1: Google Colab

1. Click a notebook link in the **Notebooks** table of the Introduction episode. It opens in Colab.
2. Click **File > Save a copy in Drive** so your changes are kept.
3. Run cells from top to bottom: click a cell and press **Shift + Enter**.
4. If Colab warns that the notebook was not written by Google, click **Run anyway**.

The notebooks use datasets built into the Plotly library, so you never need to download data.

## Part 2: Install QGIS

**QGIS** is a free, open source Geographic Information System (GIS) used to visualize spatial data,
analyze geographic patterns and design maps. It is widely used in universities, government and industry.

### Step 1: Download

1. Go to <https://qgis.org> and click **Download**.
2. Choose the **Long Term Release (LTR)** version. It is the most stable, and the lessons were written
   for it.
   - **Windows:** the standalone installer (`.msi`)
   - **macOS:** the macOS installer (`.dmg`). The first time you open QGIS, you may need to right-click
     the app and choose **Open** to get past the security warning.
   - **Linux:** follow the instructions for your distribution on the QGIS download page

### Step 2: Install

Run the installer and keep the default settings.

### Step 3: Launch

Open **QGIS Desktop** (not "QGIS with GRASS" or other variants, if several are listed). You should see the
main window.

## The QGIS interface

![The main parts of the QGIS window](qgisinterface.png){alt="Screenshot of an empty QGIS project window with yellow labels marking its main parts: the menu bar and toolbars across the top, the Browser panel at upper left listing folders and data sources, the Layers panel at lower left, the large map view on the right, and the status bar along the bottom showing coordinates, scale, magnifier, rotation and the project coordinate system."}

| Part | What it does |
|---|---|
| **Menu bar** | All commands, organized by topic (Project, Layer, Vector, Raster and so on) |
| **Toolbars** | Shortcuts for common tools such as pan, zoom and identify |
| **Browser panel** | Your files, databases and web sources, including **XYZ Tiles** basemaps |
| **Layers panel** | The layers in your project. Layers at the top are drawn on top. |
| **Map view** (canvas) | Where the map is displayed |
| **Status bar** | Coordinates under the cursor, map scale and the project's coordinate system (EPSG code) |

::::::::::::::::::::::::::::::::::::: callout

### Tip

If a panel is missing, turn it back on with **View > Panels**.

::::::::::::::::::::::::::::::::::::::::::::::::

## Troubleshooting

| Problem | Fix |
|---|---|
| QGIS will not open on macOS | Right-click the app, choose **Open**, then confirm |
| The Browser or Layers panel is missing | **View > Panels**, then tick the panel |
| A layer loaded from a web address shows nothing | Right-click the layer and choose **Zoom to Layer**; check that the address was pasted completely |
| The basemap is blank | Check your internet connection; XYZ basemaps need to be online |
| A Colab cell gives `NameError` | A cell above it was skipped; use **Runtime > Run before** |
| A Colab cell gives `ModuleNotFoundError` | Run the `!pip install` cell at the top of the notebook first |

You are all set. Start with the first episode, Introduction to Data Visualization.
