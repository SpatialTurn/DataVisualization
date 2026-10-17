---
title: 'Reference'
---

## Glossary

Alt text
:   A short written description of an image, read aloud by screen readers and shown when an image cannot
    load. For a map, it should describe what is shown and the main pattern.

Attribute table
:   The table of data attached to a vector layer; each row is a feature (a point, line or polygon) and each
    column is an attribute.

Basemap
:   A background map, such as OpenStreetMap or a grey canvas, that gives the data geographic context.

Cartogram
:   A map in which areas are resized according to a data value instead of their land area.

Categorical (qualitative) color scheme
:   Distinct hues of similar lightness, used for categories that have no order.

Choropleth map
:   A map that shades areas (such as states or counties) according to a data value. Best for rates,
    not raw counts.

Classification
:   Grouping numeric values into a small number of classes, each shown with one color. Common methods
    include equal interval, quantile, natural breaks (Jenks), standard deviation, pretty breaks and
    geometric interval.

Color vision deficiency (CVD)
:   Reduced ability to distinguish certain colors, most often reds and greens. Often called
    colorblindness.

Coordinate reference system (CRS)
:   The system that links map coordinates to places on Earth, identified by an EPSG code such as
    EPSG:4326 (latitude and longitude) or EPSG:5070 (USA Contiguous Albers Equal Area).

Diverging color scheme
:   Two hues that meet at a neutral middle, used for data with a meaningful midpoint such as zero or an
    average.

Dot density map
:   A map that places one dot for a fixed number of things (people, cases) inside each area.

Equal area projection
:   A projection that preserves the relative size of areas. Recommended for thematic maps of rates and
    densities.

Explanatory visualization
:   A figure designed to communicate one message to others.

Exploratory visualization
:   A figure made quickly to understand your own data.

Figure-ground
:   The visual separation of the main subject (figure) from its background (ground).

Legend
:   The key that explains a map's colors, symbols and units.

Map scale
:   The ratio between distance on a map and distance on the ground, such as 1:24,000. Large-scale maps
    show small areas in detail; small-scale maps show large areas.

Normalization
:   Dividing a count by a measure of size (population, area, total) to produce a rate that can be
    compared fairly between places.

North arrow
:   A map element showing the direction of north.

Print layout
:   In QGIS, the window where a map is arranged on a page with its title, legend, scale bar, north arrow
    and other elements for export.

Projection
:   A mathematical method for representing the curved Earth on a flat map. Every projection distorts
    area, shape, distance or direction.

Proportional symbol map
:   A map that sizes symbols, usually circles, according to a value at each location.

Scale bar
:   A map element that shows distances on the map.

Sequential color scheme
:   Colors that run from light to dark in one hue (or a smooth multi-hue ramp), used for ordered data
    from low to high.

Small multiples
:   A series of small charts or maps with the same axes or scales, one per group or time period, for
    easy comparison.

Symbology
:   The rules that define how features are drawn: colors, symbols, sizes and classes. In QGIS, set in
    Layer Properties > Symbology.

Visual hierarchy
:   The order in which a reader notices elements of a map or chart, controlled by size, contrast, color
    and position.

Visual variables
:   The properties of a symbol that can change to represent data: position, size, lightness, hue,
    shape, orientation and texture.

## Further reading and tools

- [ColorBrewer](https://colorbrewer2.org/): color schemes for maps, with a colorblind safe filter
- [Color Oracle](https://colororacle.org/): free color vision deficiency simulator for your screen
- [The True Size Of](https://thetruesize.com/): compare country sizes on a Mercator map
- [QGIS Training Manual](https://docs.qgis.org/latest/en/docs/training_manual/): official QGIS tutorials
- [GeoPandas mapping guide](https://geopandas.org/en/stable/docs/user_guide/mapping.html): maps in Python
- Claus Wilke, *Fundamentals of Data Visualization* (free online): <https://clauswilke.com/dataviz/>
