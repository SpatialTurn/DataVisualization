# Data Visualization and Cartography for Social Scientists

Source for the **Data Visualization** module of
[Enabling the Geospatial Turn in the Social Sciences](https://spatialturn.github.io/),
published at <https://spatialturn.github.io/DataVisualization/>.

The lesson is built with [The Carpentries Workbench](https://carpentries.github.io/sandpaper-docs/).

## Repository layout

| Folder | Contents |
|---|---|
| `episodes/` | The six lesson pages and their figures |
| `notebooks/` | Google Colab notebooks: `01a` to `01c` (Introduction) and `02a`, `02b` (Cartography in Python) |
| `learners/`, `instructors/`, `profiles/` | Setup, glossary, instructor notes and learner profiles |

| Episode file | Topic |
|---|---|
| `introduction.md` | Introduction to data visualization (with notebooks 01a to 01c) |
| `mapvisual.md` | Cartography checklists |
| `mapbasics.md` | Fundamentals of map design |
| `cartography-python.md` | Cartography in Python (with notebooks 02a and 02b; Step 8, October 2026) |
| `cartography-qgis.md` | Cartography in QGIS (rule-based styling and labels, locator inset, export) |
| `accessibility.md` | Accessibility in map design |

The "Getting Started with QGIS" episode, its screenshots and its two GeoJSON files moved to the
[Foundations module](https://github.com/SpatialTurn/Foundations) in October 2026.

Figures named `dv_*.png` in `episodes/` were generated with Python from U.S. Census Bureau, Bureau of
Labor Statistics, Natural Earth and Gapminder data. Notebooks 02a and 02b are written by
`notebook_builders/dv_cartography.py`; `ct_qgis_*.png` are QGIS 4.0 screenshots (light and dark UI) and a layout
export, with originals in `SpatialTurn_build_scripts/figure_data/dv_shots/`.

Contact: ilindsay@purdue.edu
