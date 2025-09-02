# Recipe Step Transition Network Analysis

This notebook analyzes step-to-step transitions in Indian recipes, focusing on both English and Hindi instructions. The workflow demonstrates how to extract, clean, and analyze recipe steps using network science, with a special emphasis on removing ingredient-related stopwords to reveal core cooking patterns.

---

## Workflow Overview

### 1. **Extract Unique Words from Ingredients**
- Load the recipe dataset (`IndianFoodDatasetCSV.csv`).
- Tokenize and collect all unique words from both English and Hindi ingredient columns.

### 2. **Identify Stopwords in Ingredients**
- Use NLTK's English stopword list and a custom Hindi stopword list.
- Find and print ingredient words that are stopwords.

### 3. **Remove Stopwords from Recipe Steps**
- Define a function to remove ingredient stopwords from step texts.
- Clean all step/transition texts in the recipe instruction graph.

### 4. **Build and Analyze the Transition Network**
- Load a combined recipe step graph (`all_recipes.graphml`).
- For each edge (step-to-step transition), clean the text and count transition frequencies.
- Build a directed, weighted graph where:
  - **Nodes** = unique cleaned recipe steps
  - **Edges** = transitions between steps
  - **Edge weights** = frequency of that transition across recipes

### 5. **Visualize the Transition Network**
- Plot the network for transitions that occur in more than 2 recipes.
- Node size and edge thickness reflect transition frequency.

### 6. **Network Science Analyses**
- **PageRank:** Identify the most central/influential steps in the network.
- **Degree Centrality:** Find steps that are most commonly the next or previous step.
- **Community Detection:** Discover clusters of steps that often occur together.
- **Network Statistics:** Print number of nodes, edges, density, and strongly connected components.

---

## Key Insights

- **Stopword removal** merges similar steps, revealing true core transitions and increasing transition frequencies.
- **Network analysis** highlights the most central steps, common sub-processes, and the overall structure of recipe instructions.
- **Visualization** helps identify hubs, clusters, and frequent flows in Indian cooking.

---

## Requirements

- Python 3.x
- pandas
- networkx
- matplotlib
- nltk

Install requirements with:
```bash
pip install pandas networkx matplotlib nltk
```

---

## Files

- `IndianFoodDatasetCSV.csv` — Recipe dataset with ingredient and step columns.
- `all_recipes.graphml` — Pre-built graph of recipe steps and transitions.
- `stop_words.ipynb` — This analysis notebook.

---

## Usage

1. Place the dataset and graphml file in the same directory as the notebook.
2. Run the notebook step by step.
3. Explore and visualize the recipe step transition network.

---

## Example Outputs

- **Top transitions** (after stopword removal)
- **Network plot** of step transitions
- **Most central steps** by PageRank
- **Community clusters** of steps

---


*This notebook is designed for culinary data mining, recipe process analysis, and network science education. Contributions
