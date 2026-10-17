---
title: Setup
---

This module uses two free tools:

- **Google Colab** for the Python notebooks in the Introduction episode. It runs in your web browser,
  so there is nothing to install.
- **QGIS** for the Accessibility episode. It is a desktop program you install once.

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

Follow the installation steps on the [central Setup page](https://spatialturn.github.io/Foundations/learners/setup.html) of the Foundations module, which also
shows the parts of the QGIS window. If QGIS is new to you, work through the Foundations module's
[Getting Started with QGIS](https://spatialturn.github.io/Foundations/qgisintro.html) episode before the Accessibility episode.

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
