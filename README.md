# Data Visualization and Cartography for Social Scientists

Source for the **Data Visualization** module of
[Enabling the Geospatial Turn in the Social Sciences](https://spatialturn.github.io/),
published at <https://spatialturn.github.io/DataVisualization/>.

The lesson is built with [The Carpentries Workbench](https://carpentries.github.io/sandpaper-docs/).

## Repository layout

| Folder | Contents |
|---|---|
| `episodes/` | The five lesson pages and their figures |
| `notebooks/` | Google Colab notebooks linked from the Introduction episode (`01a` to `01c`) |
| `data/` | Small GeoJSON files loaded by URL in the QGIS episode |
| `learners/`, `instructors/`, `profiles/` | Setup, glossary, instructor notes and learner profiles |

| Episode file | Topic |
|---|---|
| `introduction.md` | Introduction to data visualization (with notebooks 01a to 01c) |
| `mapvisual.md` | Cartography checklists |
| `mapbasics.md` | Fundamentals of map design |
| `qgisintro.md` | Getting started with QGIS |
| `accessibility.md` | Accessibility in map design |

### Data

| File | Contents | Source |
|---|---|---|
| `data/indiana_counties.geojson` | Indiana counties with 2012 population, land area, density and 2016 unemployment | U.S. Census Bureau; U.S. Bureau of Labor Statistics (via plotly datasets) |
| `data/alaska_airports.geojson` | 76 Alaska airports with name, use and elevation | QGIS sample data |

Figures named `dv_*.png` in `episodes/` were generated with Python from U.S. Census Bureau, Bureau of
Labor Statistics, Natural Earth and Gapminder data. Screenshots of QGIS were taken by the authors.

Contact: ilindsay@purdue.edu
