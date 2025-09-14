# K-means Clustering from Scratch (NumPy) — with Image Compression

[![Python 3.12](https://img.shields.io/badge/python-3.12-blue.svg)](https://www.python.org/downloads/)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![NumPy](https://img.shields.io/badge/NumPy-Scientific%20Computing-013243.svg)](https://numpy.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557c.svg)](https://matplotlib.org/)

A minimal, educational implementation of K-means clustering using pure NumPy, demonstrated in a Jupyter notebook. It visualizes clustering on a 2D toy dataset and applies K-means to compress an image by reducing its color palette.

- Notebook: [KMeans.ipynb](KMeans.ipynb)
- Utilities: [utils.py](utils.py)
- Sample data: [data/ex7_X.npy](data/ex7_X.npy)
- Sample image: [images/bird_small.png](images/bird_small.png)
- Example figures: [images/figure1.png](images/figure1.png), [images/figure2.png](images/figure2.png), [images/figure3.png](images/figure3.png)

## What this project does

- Implements the core K-means steps:
  - Cluster assignment: [`find_closest_centroids`](KMeans.ipynb) assigns each example to the nearest centroid by minimizing $||x - \mu_j||_2$.
  - Centroid update: [`compute_centroids`](KMeans.ipynb) recomputes centroids as the mean of assigned points.
- Orchestrates the loop: [`run_kMeans`](KMeans.ipynb) iterates assignment and update steps.
- Initializes centroids: [`kMeans_init_centroids`](KMeans.ipynb) picks random examples as starting centroids.
- Visualizes progress on a toy dataset using plotting helpers from [utils.py](utils.py):
  - [`plot_data_points`](utils.py), [`draw_line`](utils.py), [`show_centroid_colors`](utils.py)
- Applies K-means to compress an RGB image to K colors (e.g., K=16).

## Why it’s useful

- Clear, from-scratch NumPy implementation (no scikit-learn).
- Step-by-step visualization of K-means convergence.
- Practical example: lossy image compression with a controllable palette size.
- Small codebase that’s ideal for learning, teaching, or quick experimentation.

## Project structure

- [KMeans.ipynb](KMeans.ipynb): Main walkthrough notebook (toy dataset demo + image compression).
- [utils.py](utils.py): Plotting helpers for 2D and RGB visualizations.
- [data/ex7_X.npy](data/ex7_X.npy): 2D dataset used in the toy example.
- [images/](images/): Input image and example figures.

## Getting started

### Prerequisites

- Python 3.12+
- pip
- VS Code (recommended) with the Jupyter extension or Jupyter Lab/Notebook

### Installation

```bash
# (optional) create and activate a virtual environment
python -m venv .venv
# Windows
. .venv\Scripts\activate
# macOS/Linux
# source .venv/bin/activate

# install dependencies
pip install numpy matplotlib jupyter
```

### Run the notebook

- Open [KMeans.ipynb](KMeans.ipynb) in VS Code (with Jupyter support) or launch:

```bash
jupyter notebook
```

- Execute cells top-to-bottom. The notebook:
  - Runs K-means on the toy dataset from [data/ex7_X.npy](data/ex7_X.npy)
  - Compresses [images/bird_small.png](images/bird_small.png) to K colors
  - Displays intermediate and final results (see [images/figure1.png](images/figure1.png), [images/figure2.png](images/figure2.png), [images/figure3.png](images/figure3.png))

## Configuration

- Number of clusters: set `K` (e.g., 8, 16, 32).
- Iterations: set `max_iters`.
- Randomness: call `np.random.seed(<int>)` before [`kMeans_init_centroids`](KMeans.ipynb) for reproducible runs.
- Input image: replace [images/bird_small.png](images/bird_small.png) with your own image (ensure it loads via `plt.imread`).


## Maintainers

- Maintainer: Aarush Sharma