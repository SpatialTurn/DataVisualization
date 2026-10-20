---
title: "Cartography in Python"
teaching: 40
exercises: 45
---

:::::::::::::::::::::::::::::::::::::: questions

- How do I turn a correct map into a finished one that others can read and print?
- How should layers, labels and a basemap be ordered and styled?
- When do small multiples need a shared scale?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Style and order layers by their role: subject, supporting features, context and reference
- Label features legibly and by rule, with halos
- Add a basemap responsibly, a locator inset, a true scale bar and a north arrow
- Build small multiples with separate or shared classifications
- Export maps for print and screen

::::::::::::::::::::::::::::::::::::::::::::::::

## From a correct map to a finished map

The [Fundamentals of Map Design](mapbasics.md) episode covers what a thematic map shows: map elements,
normalization, classification and color. This episode is about **finishing**: turning a correct choropleth into
a map that a reader outside your project understands at a glance and that prints cleanly. The running example
is the share of households without a car in Lafayette and West Lafayette, Indiana, with parks and city limits on
top.

## Visual hierarchy, layer by layer

Every layer has a role, and its styling should match it:

| Role | Example | Styling |
|---|---|---|
| **Subject** | The choropleth of car-free households | Strong color, full opacity |
| **Supporting features** | Parks, city limits | Distinct but secondary: one hue, thin or dashed lines, some transparency |
| **Context** | Basemap, neighboring areas | Quiet: gray, low contrast |
| **Reference** | Labels, scale bar, north arrow, source | Small, legible, never decorative |

**Order** follows from the roles: polygons of the subject at the bottom, supporting outlines and points above
them, labels on top, and the basemap underneath everything. A layer on top of a choropleth needs either no
fill, transparency, or a strong outline so it does not hide what is underneath.

## Labels

Labels are reference information. They should be findable, legible and not in the way.

- **Label sparingly.** Label what the reader needs to orient themselves or to understand the story: the largest
  parks, the two city names. Labeling all 68 parks makes none of them readable.
- **Use a halo** (a thin outline in the background color, called a *buffer* in QGIS). It keeps text readable over
  any color and is the single most effective labeling technique.
- **Use type to signal kind.** Common conventions: italics for water and areas (rivers, parks, neighborhoods),
  upright for places and points, larger or capitalized type for more important names.
- **Place labels inside or next to their feature**, never across a boundary. For polygons, a point guaranteed to
  be inside (a "representative point" or "point on surface") is safer than the centroid, which can fall outside an
  L-shaped polygon.
- **Choose rules, not exceptions.** "Label parks over 30 hectares" is reproducible; hand-picking labels is not.

## Basemaps

A tiled basemap (OpenStreetMap, Esri, CARTO, Stamen) adds streets and place names for free, at a cost: visual
noise, a dependence on an online service, and **license conditions**. Choose a quiet, gray basemap for thematic
maps, keep its **attribution** text, and do not rely on it for print if you need full control or very high
resolution. Basemap tiles are in Web Mercator (EPSG:3857); software reprojects them to your map's CRS, which can
blur their labels slightly.

## Locator insets, scale bars and north arrows

- A **locator inset** (a small map of the state or country with the study area highlighted) answers "where is
  this?" for readers who do not know the area. It does not need a scale bar or legend of its own.
- A **scale bar** is only true on a map in a **projected** CRS with little distortion over the map (a UTM zone or
  a state plane for a county). In degrees or Web Mercator at large extents the scale changes across the map, and
  a single bar misleads.
- A **north arrow** is only essential when north is not up, but it is cheap and many readers expect one.

## Small multiples and shared scales

To compare several variables or years, repeat the same map in a grid of **small multiples**. The eye compares
patterns across panels far better than it decodes several variables in one crowded map.

Decide deliberately whether panels **share a classification**:

- **Same variable or same units** (one rate in different years, two rates you want to compare): use the **same
  class breaks and colors** in every panel, or the same dark color will mean different values.
- **Different variables** (income in dollars, children in percent): each panel needs its own classes and legend,
  and the reader compares patterns, not colors.

## Export

| Destination | Format | Notes |
|---|---|---|
| Print, a paper, a poster | **PDF** (vector) | Sharp at any size; set the page or figure size to the printed size |
| Slides, a website | **PNG** at 200 to 300 dpi | PNG keeps sharp edges; JPEG blurs lines and text |
| Further editing (Illustrator, Inkscape) | **SVG** | Every element stays editable |

Check the exported file, not just the screen: font sizes, line widths and legend spacing often look different
at print size.

::::::::::::::::::::::::::::::::::::: callout

## The same map in QGIS

The [Cartography in QGIS](cartography-qgis.md) episode makes the same map with rule-based styling and labeling and
a print layout with a locator inset. Notebook 01c of this module covers the basics (choropleths, classification,
palettes) used here.

::::::::::::::::::::::::::::::::::::::::::::::::

## The toolkit in code

| Task | Python |
|---|---|
| Layer order | `zorder=` on each `plot()` call; `alpha=` for transparency |
| Zoom | `ax.set_xlim()`, `ax.set_ylim()` from a layer's `total_bounds` |
| Labels with halos | `ax.text(..., path_effects=[patheffects.withStroke(linewidth=3, foreground="white")])` at `representative_point()` |
| Basemap | `contextily.add_basemap(ax, crs=layer.crs, source=contextily.providers.Esri.WorldGrayCanvas)` |
| Legend for several layers | Build `Patch` and `Line2D` handles and pass them to `ax.legend(handles=...)` |
| Locator inset | `inset = ax.inset_axes([left, bottom, width, height])`, then plot the state and the highlighted county |
| Scale bar | `ax.add_artist(ScaleBar(dx=1, units="m"))` from `matplotlib-scalebar`, for maps in meters |
| Shared classes | `scheme="UserDefined", classification_kwds={"bins": [...]}` in every panel |
| Export | `fig.savefig("map.pdf")`, `fig.savefig("map.png", dpi=300, bbox_inches="tight")` |

:::::::::::::::::::::::::::::::::::: challenge

## Challenge 1: What is wrong with this map?

A map of poverty rates by tract uses a satellite basemap at full opacity, red and green classes, labels for every
street, a scale bar on a Web Mercator map of the whole United States, and no source line. List the problems and
a fix for each.

:::::::::::::::: solution

- Satellite basemap: too busy for a thematic map; use a quiet gray basemap or none, and keep the attribution.
- Red and green classes: unreadable for many readers with color vision deficiency, and a diverging scheme for a
  one-directional rate; use a sequential palette (see the Accessibility episode).
- Labels for every street: clutter; label only what orients the reader.
- Scale bar on a national Web Mercator map: the scale varies greatly with latitude; drop it or use an equal-area
  projection and a note.
- No source line: add the dataset and year.

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::: challenge

## Challenge 2: Shared scale or not?

You make four small multiples. Which need a shared classification? (a) Households without a car in 2015, 2018,
2021 and 2024. (b) Poverty rate, median income, share of children and population density in 2024.

:::::::::::::::: solution

(a) **Shared**: the same variable over time, so the same color must mean the same value in every year. Compute
breaks from all four years together. (b) **Separate**: four variables in different units; give each panel its
own classes and legend, and let readers compare patterns.

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: keypoints

- Style each layer by its role; the subject is strong, context is quiet
- Label sparingly, by rule, with halos; italics for areas and water
- Use quiet basemaps and keep their attribution; scale bars need a projected CRS
- A locator inset shows where the map is; small multiples compare, with shared breaks only for comparable values
- Export PDF for print and PNG at 200 to 300 dpi for screens, and check the exported file

::::::::::::::::::::::::::::::::::::::::::::::::

## Notebooks

| Notebook | What you will do |
|---|---|
| <a href="https://colab.research.google.com/github/SpatialTurn/DataVisualization/blob/main/notebooks/02a_Layers_Labels_and_Basemaps.ipynb" target="_blank">2a. Layers, Labels and Basemaps</a> | Stack tracts, parks and city limits, zoom to the cities, label the largest parks with halos, add a basemap and a multi-layer legend |
| <a href="https://colab.research.google.com/github/SpatialTurn/DataVisualization/blob/main/notebooks/02b_Insets_Small_Multiples_and_Export.ipynb" target="_blank">2b. Insets, Small Multiples and Export</a> | Add a locator inset, a scale bar and a north arrow, compare four variables in small multiples, share a scale, and export PDF and PNG |
