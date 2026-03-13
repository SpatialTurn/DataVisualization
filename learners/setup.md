---
title: "Setup"
---

## Overview

To participate in the **Data Visualization** module, you will need:

- **Python 3.10 or newer** (3.11–3.12 recommended in local setups)
- The following Python packages:
  - pandas (data handling)
  - matplotlib (core plotting)
  - seaborn (statistical visualizations)
  - (optional but recommended) jupyterlab or notebook (interactive work)
  - (optional) plotly (interactive charts in later episodes)
- A code editor or notebook interface
- Sample datasets (provided as a zip file)

We offer **two main setup paths**:

1. **Google Colab** (recommended for beginners / no installation needed)
2. **Local installation** with `Anaconda Navigator` (great for offline work and full control)

## Option 1: Google Colab (Zero Installation – Recommended for Most Learners)

Google Colab is a free, cloud-based Jupyter notebook environment hosted by Google. It runs entirely in your browser, requires only a Google account, and comes with pandas, matplotlib, seaborn, and many other data science libraries **pre-installed**.

### Steps

1. Go to → https://colab.research.google.com
2. Sign in with your Google account (or create one if needed).
3. Click **New notebook** (or File → New notebook).
4. (Optional) Rename it: File → Rename (e.g., "Data Viz Workshop – Aniket").
5. Test the libraries right away by running this in the first cell (Shift+Enter to execute):

   ```python
   import pandas as pd
   import matplotlib.pyplot as plt
   import seaborn as sns
   import plotly.express as px   # optional – usually pre-installed too

   print("pandas version:", pd.__version__)
   print("matplotlib version:", plt.matplotlib.__version__)
   print("seaborn version:", sns.__version__)
   print("plotly version:", px.__version__ if 'px' in globals() else "not imported")

   # Quick test plot (should show inline)
   tips = sns.load_dataset("tips")  # built-in Seaborn dataset
   sns.histplot(data=tips, x="total_bill", hue="time")
   plt.title("Test: Restaurant Tips Distribution")
   plt.show()
   ```
6. Installing extra packages (rarely needed, but if something is missing or outdated):Python

```python
!pip install --upgrade seaborn plotly
```

(The `!` runs shell commands in Colab/Jupyter Notebook.)

## Advantages of Colab for this workshop

- No software installation
- Free GPU/TPU if needed later
- Easy sharing (File → Share)
- Autosaves to Google Drive
- Perfect for following along with instructor demos

**Tip**: Upload your own data files via the left sidebar (Files tab → Upload) or mount Google Drive:
Python

```python
from google.colab import drive
drive.mount('/content/drive')
# Then read files like pd.read_csv('/content/drive/MyDrive/penguins.csv')
```

## Option 2: Local Installation (Anaconda Navigator – For Offline / Advanced Use)

Use this if you prefer working without internet or need a persistent environment.

1. Download and install Anaconda Navigator:

- https://www.anaconda.com/products/navigator
- Choose your OS installer (Python 3.x version) → follow defaults

2. You should find multiple apps after installation. 

- Launch `Jupyter Notebook`
- If you do not find a package simply add `!pip` followed by the name of the package in code cell to install it locally.

## Troubleshooting

- **Colab:** Plots not showing? Add %matplotlib inline at the top (usually automatic).
- **Local:** package not found: Open terminal or code cell in jupyter notebook and `!pip` install package.
- **Need help?** Raise hand during workshop or check Carpentries Python setup guide.

You're all set! Proceed to Introduction to Data Visualization or Creating Your First Plots.

Happy visualizing!

