# Structural Analysis of an Ingredient Co-occurrence Network

This repository contains the code, data, and resources for the **Final Individual Report** on Complex Networks. The project analyzes a food ingredient network where nodes represent ingredients and edges represent shared flavour compounds.

## Project Overview

The goal of this study is to analyze the structure, centrality, and communities of the flavour network. The analysis is performed in two independent Jupyter Notebooks:

### 1. `ingredient_net_analysis.ipynb`
This is the main script. It performs the core structural analysis on the **unweighted** network:
* **Basic descriptors:** Calculation of density, clustering coefficient, and average path lengths.
* **Degree distribution:** Fitting of Power Law, Log-Normal, and other distributions to the empirical data. It includes a specific goodness-of-fit comparison.
* **Centrality:** Calculation of degree, betweenness, closeness, and eigenvector centralities. It also analyzes centrality scores and node rankings for the top 25 ingredients.
* **Null Models:** Comparison of the real network against Erdős-Rényi, Barabási-Albert, and Configuration Model ensembles (10 realizations each).
* **Community Detection:** Application of Louvain, Greedy Modularity and Label Propagation algorithms with the correspoding partition quality metrics.
* **Visualization:** Provides a fast internal visualization of communities and an export for Gephi (.gexf) to allow for more professional network styling.

### 2. `weighted_computations.ipynb`
This notebook focuses on the **weighted** network analysis:
* **Edge Weights:** Edges are weighted based on the number of shared chemical compounds between ingredients.
* **Weighted Centrality:** Re-calculation of centrality metrics using weights.
* **Comparison:** Analysis of how the rankings change when weights are considered (comparing weighted vs. unweighted top 25 nodes).

---

## System Specifications and Requirements

* **Operating System**: This project was developed and tested on **Windows 11**.
* **Python Version**: Python 3.13.7.
* **Libraries**: All required packages are listed in `requirements.txt`.

To install the dependencies, run:
```bash
pip install -r requirements.txt
```

## File Structure

Since the scripts save outputs directly to the directory where they are executed, the project folder should look like this:

```text
.
├── data/
│   └── ingredients_network.csv       # The raw dataset
├── ingredient_net_analysis.ipynb
├── weighted_computations.ipynb
├── requirements.txt
├── [Generated PDF Figures]    # Created after running the notebooks
└── [Generated GEXF Files]    # Created for Gephi visualization
└── README.md
