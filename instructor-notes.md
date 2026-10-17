---
title: 'Instructor Notes'
---

## Overall approach

- This module mixes **concepts** (Cartography Checklists, Fundamentals of Map Design), **Python**
  (the Introduction notebooks) and **QGIS** (Getting Started with QGIS, Accessibility). Make sure
  learners have both a Google account and QGIS installed before the session; QGIS installation is the
  most common delay.
- Every figure in the concept episodes was generated from open data (U.S. Census Bureau, Bureau of Labor
  Statistics, Natural Earth, Gapminder) with code, so the examples are reproducible and properly credited.
- All data is read from the web. The notebooks use Plotly's built-in datasets; the QGIS episode loads
  GeoJSON files from this repository's `data/` folder by URL.
- Suggested timing for a half day: Introduction (30 min plus notebook 1a), Checklists (30 min), Map
  Design (60 min), QGIS (75 min), Accessibility (30 min). Notebooks 1b and 1c work well as take-home
  material.

## Episode by episode

### Introduction to Data Visualization

- Start with the misleading axis figure; it gets an immediate reaction and makes the point that correct
  data can still mislead.
- Notebook 1a needs no prior plotting experience. Notebook 1c includes an optional Census section that
  skips itself when no API key is entered, so **Runtime > Run all** works for everyone.

### Cartography Checklists

- Ask learners to bring (or find) a map from the news and apply the checklist to it during the
  discussion.
- The "bad map" is deliberately terrible; ask the group to list every problem before revealing the list.

### Fundamentals of Map Design

- Normalization and classification are the two ideas learners most often get wrong in their own work.
  Spend time on the count versus percent figure and the six classification maps.
- The classification figure uses Indiana population density, which is strongly skewed. Point out how
  equal interval puts almost everything in one class, and show the histogram figure to explain why.
- Use The True Size Of website live; dragging Russia or Greenland to the equator is memorable.

### Getting Started with QGIS

- Loading from a web address (Layer > Add Layer > Add Vector Layer > Protocol: HTTP(S)) avoids file
  downloads and path problems. If a network blocks it, the same GeoJSON files can be downloaded from the
  repository's `data/` folder and loaded as files.
- In QGIS, the OpenStreetMap basemap works normally. (In Colab it does not, which is why the notebooks use
  an Esri basemap.)
- Learners often press **OK** instead of **Apply** while comparing classification modes; encourage
  **Apply** so the dialog stays open.
- Remind learners to rename layers before making a legend.

### Accessibility in Map Design

- Turn on **View > Preview Mode > Simulate Color Blindness (Deuteranope)** on the projector with a
  red-green map; it is the most convincing demonstration.
- Prevalence figures (about 8% of men and 0.5% of women) are for people of Northern European ancestry;
  rates are lower in many other populations.

## Common problems

| Symptom | Likely cause | Fix |
|---|---|---|
| QGIS will not open on macOS | Security setting | Right-click the app and choose **Open** |
| A web layer loads but nothing appears | Layer is off screen or under the basemap | Right-click the layer > **Zoom to Layer**; drag it above the basemap |
| Graduated symbology shows one color | Wrong field (text or an ID) selected | Choose a numeric field such as `density` |
| Colab `NameError` | A cell was skipped | **Runtime > Run before** |
| Interactive map shows "403" or "API key required" | OpenStreetMap or CARTO tiles blocked in Colab | Use `tiles="Esri.WorldGrayCanvas"` |
| Census section in notebook 1c fails | Key missing, mistyped or not activated | Check the key and its activation email, or skip the section |
