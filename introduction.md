---
title: "Introduction to Data Visualization"
teaching: 45
exercises: 30
---

:::::::::::::::::::::::::::::::::::::: questions
- What exactly is data visualization and how does it differ from simple charts?
- Why do humans understand visualized data much faster than raw numbers or tables?
- What are the real advantages and hidden pitfalls of using visuals in data analysis?
- How does visualization help (or complicate) working with big data?
- Which tools are most suitable for beginners, intermediate users, and advanced programmers?
- What makes a visualization "good" versus "misleading"?
::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives
- Define data visualization and explain its core purpose
- List at least five advantages and three disadvantages of data visualization
- Describe how visualization addresses challenges posed by big data
- Identify and differentiate between exploratory and explanatory visualizations with real-world examples
- Compare popular open-source and commercial tools for creating visualizations
- Recognize key principles of effective visualization design
- Understand ethical considerations and accessibility best practices
::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: keypoints
- Data visualization turns numbers into stories that the human brain can understand quickly.
- Good visualizations reveal patterns, trends, and outliers that are invisible in spreadsheets.
- Poor design can mislead audiences more powerfully than raw data ever could.
- Big data demands interactive, scalable, and often multi-dimensional visualizations.
- Choose the right tool for your audience and skill level — start simple and iterate.
- Always prioritize clarity, honesty, and accessibility over visual flair.
::::::::::::::::::::::::::::::::::::::::::::::::

## What Is Data Visualization?

**Data visualization** is the graphical representation of information and data.  
Instead of showing rows and columns of numbers, it uses charts, graphs, maps, diagrams, and interactive dashboards to make patterns, trends, relationships, and outliers immediately understandable.

Think of it as **data storytelling** with graphics. A well-designed visualization does in seconds what a 10-page spreadsheet cannot: it lets the human brain — which processes images 60,000 times faster than text — grasp complex information at a glance.

In the Carpentries context, data visualization is not just "making pretty pictures." It is a core skill that bridges **data wrangling** (what you learned in previous episodes) and **data-driven decision making**.

## Why Is Data Visualization Important?

1. **Humans are visual creatures**  
   Our brains devote more than 50% of their processing power to vision. A bar chart showing sales growth is far more memorable than a table of 50 monthly figures.

2. **Reveals what numbers hide**  
   - Trends over time  
   - Clusters and correlations  
   - Outliers and anomalies  
   - Geographic patterns  
   - Distributions and variability  

3. **Enables faster decision-making**  
   Executives, scientists, journalists, and policymakers routinely use visualizations to justify budgets, publish papers, or influence public opinion.

4. **Democratizes data**  
   A clear chart can be understood by domain experts and non-technical stakeholders alike.

5. **Supports both exploration and explanation**  
   - **Exploratory visualizations** help *you* discover insights while analyzing data.  
   - **Explanatory visualizations** help *others* understand your discoveries.

## Advantages of Data Visualization

- **Speed**: Spot trends in seconds instead of hours.
- **Clarity**: Reduce cognitive load — one image can replace thousands of numbers.
- **Pattern recognition**: Humans excel at seeing lines, clusters, and shapes.
- **Engagement**: Colorful, interactive visuals capture attention and improve retention.
- **Storytelling power**: Turn dry statistics into compelling narratives.
- **Error detection**: Visuals often reveal data quality problems (missing values, typos, impossible ranges) that automated checks miss.
- **Accessibility for diverse audiences**: Good visuals can communicate across language barriers and technical skill levels.

## Disadvantages and Risks

- **Misleading results**: A truncated y-axis, 3D effects, or cherry-picked colors can completely distort the truth (classic example: the "exploding" pie chart).
- **Chartjunk** (Edward Tufte's term): Decorative elements that add noise without adding information.
- **Time investment**: Creating a professional, publication-ready visualization can take longer than the analysis itself.
- **Skill gap**: Requires both analytical thinking *and* design sensibility.
- **Over-simplification**: Complex multi-variable relationships can be flattened into something misleading.
- **Accessibility barriers**: Poor color contrast or lack of alt text excludes people with color blindness or screen readers.

> **Callout: The "lying with charts" phenomenon**  
> Always ask: "Does this visual tell the *whole* story, or just the story I want to tell?"

## Big Data and the Need for Visualization

The explosion of big data (volume, velocity, variety, veracity) has made visualization not just helpful — but **essential**.

- **Volume**: A 1-million-row dataset is impossible to read. A heatmap or density plot shows the entire distribution instantly.
- **Velocity**: Real-time dashboards (stock markets, COVID-19 trackers, IoT sensor networks) update every second.
- **Variety**: Combining structured tables, text, images, and geospatial data requires multi-layered visuals (e.g., a map with overlaid time-series).
- **Dimensionality**: With 50+ variables, we use techniques like PCA, t-SNE, or parallel coordinates plots to reduce complexity.

Modern big-data visualizations are often:
- Interactive (zoom, filter, hover tooltips)
- Scalable (handle millions of points without crashing)
- Collaborative (shared dashboards in Tableau Server, Power BI, or Plotly Dash)

## Real-World Examples

### Simple but powerful
- **Line chart**: Global temperature rise 1880–2025 (clear upward trend)
- **Bar chart**: Top 10 countries by renewable energy adoption
- **Scatter plot**: Relationship between study hours and exam scores (with regression line)

### More advanced
- **Heatmap**: Correlation matrix of 20 variables in a genomics dataset
- **Treemap**: Breakdown of a company’s revenue by department and region
- **Network graph**: Social media connections or protein interaction maps
- **Choropleth map**: U.S. election results or COVID case rates by county
- **Animated bubble chart** (Hans Rosling style): 200 years of health and wealth data showing global progress

### Good vs. Bad examples (you will practice these in exercises)
- **Good**: Minimalist line chart with clear labels and honest scale.
- **Bad**: 3D exploding pie chart with 12 slices, rainbow colors, and no legend.

## Popular Tools — From Beginner to Advanced

| Skill Level      | Tool/Library                  | Best For                          | Open Source? | Carpentries Recommendation |
|------------------|-------------------------------|-----------------------------------|--------------|----------------------------|
| Beginner        | Excel / Google Sheets        | Quick bar/line/pie charts        | No          | Great starting point      |
| Beginner–Intermediate | Tableau Public / Power BI   | Interactive dashboards           | Partial     | Excellent for non-coders  |
| Intermediate    | Python + Matplotlib/Seaborn  | Publication-quality static plots | Yes         | **Highly recommended**    |
| Intermediate–Advanced | Python + Plotly             | Interactive web-ready charts     | Yes         | Perfect for sharing       |
| Advanced        | R + ggplot2                  | Statistical graphics             | Yes         | Data Carpentry favorite   |
| Advanced        | JavaScript + D3.js           | Fully custom web visualizations  | Yes         | For web developers        |
| All levels      | Observable / Vega-Lite       | Notebook-style interactive viz   | Yes         | Modern & flexible         |

In this workshop series we will focus primarily on **Python** (Matplotlib, Seaborn, Plotly) and briefly touch on R’s ggplot2 because they integrate seamlessly with the data-cleaning skills you already learned.

## Principles of Effective Visualization (The "Rules")

Inspired by Edward Tufte, William Cleveland, and Alberto Cairo:

1. **Maximize data-ink ratio** — remove everything that is not data.
2. **Use small multiples** instead of overloading one chart.
3. **Choose the right chart type** for the message (never use pie charts for >5 categories!).
4. **Label everything** clearly — titles, axes, legends, units.
5. **Be honest** — never truncate axes without disclosure.
6. **Consider color carefully** — use colorblind-friendly palettes (ColorBrewer, viridis).
7. **Make it accessible** — alt text, high contrast, patterns in addition to color.
8. **Tell a story** — guide the viewer’s eye with titles, annotations, and sequence.

## Ethical Considerations

- Visualizations can influence policy, investment, and public opinion.
- Avoid cherry-picking time windows or subsets.
- Disclose data sources and limitations.
- Respect privacy (especially with geospatial or personal data).

## Challenges You Will Face (and How We Solve Them)

- Too many variables → dimensionality reduction + faceting
- Performance with millions of points → sampling, aggregation, or WebGL-based tools
- Reproducibility → always save code alongside the image
- Version control → store plots in Git (we’ll show you how)

## Key Takeaways

Data visualization is not decoration — it is **analysis made visible**.  
Mastering it will transform how you explore data, how you communicate results, and how much impact your work has.

In the next episodes we will:
- Build your first publication-ready plots in Python.
- Learn how to critique and improve existing visualizations.
- Combine visualization with statistical analysis.

---

**Exercise (30 min)**  
1. Open the google collab file in `Start Here` Module [here](https://colab.research.google.com/github/SpatialTurn/DataCollection-Notebooks/blob/main/Census/Intro_Ploting.ipynb). Make sure to make your own copy to save progress! 
2. Alternatively, refer the Bad and Good Plotting techniques in this module. Understand what the basic requirements of producing a good plot looks like. 

---