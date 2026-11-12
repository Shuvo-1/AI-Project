
# AI Project: Performance Comparison of IDS and Bidirectional BFS

## Project Overview

This project compares the performance of two Artificial Intelligence search algorithms:

- **Iterative Deepening Search (IDS)**
- **Bidirectional Breadth-First Search (Bidirectional BFS)**

Both algorithms are implemented in C++ and tested on the **Stanford SNAP Road Network (roadNet-PA)** dataset.

The main objective is to analyze and compare the algorithms based on their search efficiency, execution time, memory consumption, and node exploration behavior.

## Algorithms Used

### 1. Iterative Deepening Search (IDS)

Iterative Deepening Search combines the depth-first search approach with increasing depth limits.

It repeatedly performs depth-limited DFS until the destination node is found.

**Key characteristics:**
- Uses a depth limit that increases iteratively.
- Requires relatively low search memory.
- May expand nodes repeatedly across different iterations.
- Finds an optimal path when all edges have equal cost.

### 2. Bidirectional Breadth-First Search (Bidirectional BFS)

Bidirectional BFS performs two simultaneous searches:

- Forward search from the source node.
- Backward search from the destination node.

The algorithm expands complete BFS levels, choosing the smaller frontier, until the searches meet and the shortest path is identified.

**Key characteristics:**
- Searches from both directions.
- Uses two search frontiers.
- Can reduce the search space significantly.
- Finds the shortest path in an unweighted graph.

## Dataset

**Dataset:** Stanford SNAP Road Network – Pennsylvania (roadNet-PA)

**Source:** Stanford Large Network Dataset Collection (SNAP)

Dataset link: https://snap.stanford.edu/data/roadNet-PA.txt.gz

The dataset represents a road network as an edge list. Each valid line contains two node IDs representing a connection between two nodes.

The programs load the dataset into an undirected adjacency-list graph.

## Test Cases

Both algorithms use exactly the same five source-destination pairs to ensure a fair comparison.

| Test Case | Source | Destination |
|---|---:|---:|
| 1 | 0 | 396 |
| 2 | 0 | 3063 |
| 3 | 0 | 3588 |
| 4 | 0 | 2732 |
| 5 | 0 | 38 |

## Performance Metrics

The project evaluates both algorithms using the following metrics:

| Metric | Description |
|---|---|
| Shortest Path Length | Number of edges in the resulting path |
| Expanded Nodes | Total number of expanded nodes |
| Repeated Node Expansions | Number of nodes expanded more than once |
| Edge Scans | Total number of edges examined |
| Unique Nodes Encountered | Number of distinct nodes encountered |
| Search Time | Time taken by the search algorithm (ms) |
| Peak Auxiliary Memory | Maximum estimated auxiliary memory usage (MB) |

The results are automatically saved in a CSV file named `comparison_results.csv`.

## Technologies Used

- **C++17** – Implementation of search algorithms
- **Python** – Data analysis and visualization
- **Pandas** – CSV data processing
- **NumPy** – Numerical operations
- **Matplotlib** – Performance comparison graphs
- **Google Colab** – Development and execution environment
- **GCC/G++** – C++ compilation

## Project Structure

```text
AI-Project/
│
├── IDS.cpp
├── Bidirectional_BFS.cpp
├── comparison_results.csv
│
├── graphs/
│   ├── expanded_nodes.png
│   ├── repeated_node_expansions.png
│   ├── edge_scans.png
│   ├── unique_nodes.png
│   ├── search_time.png
│   ├── peak_auxiliary_memory.png
│   └── shortest_path_length.png
│
├── roadNet-PA.txt
│
├── AI_Project.ipynb
│
└── README.md
```

*Note: The dataset, generated CSV, graphs, and notebook are produced or downloaded during the project workflow. Include the files in your repository only if you have uploaded them.*

## Installation and Execution

### 1. Clone the Repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd YOUR_REPOSITORY_FOLDER
```

### 2. Download the Dataset

Download the Pennsylvania road network dataset:

```bash
wget https://snap.stanford.edu/data/roadNet-PA.txt.gz
```

Extract the dataset:

```bash
gunzip roadNet-PA.txt.gz
```

### 3. Compile the C++ Programs

Compile IDS:

```bash
g++ -O2 -std=c++17 IDS.cpp -o IDS
```

Compile Bidirectional BFS:

```bash
g++ -O2 -std=c++17 Bidirectional_BFS.cpp -o BiBFS
```

### 4. Run the Algorithms

Run IDS:

```bash
./IDS roadNet-PA.txt
```

Run Bidirectional BFS:

```bash
./BiBFS roadNet-PA.txt
```

Both programs execute the same five test cases and save their results in `comparison_results.csv`.

### 5. Generate Performance Graphs

Install the required Python libraries:

```bash
pip install pandas matplotlib numpy
```

Run the Python visualization code from the project notebook to generate the comparison graphs.

The graphs are saved in the `graphs/` directory.

## Expected Outputs

After successful execution, the project generates:

1. Search results for all five test cases.
2. Shortest path length for each successful search.
3. Search performance statistics.
4. `comparison_results.csv` containing the collected metrics.
5. Seven individual graphs comparing the two algorithms.

## Conclusion

This project provides an experimental comparison between Iterative Deepening Search and Bidirectional Breadth-First Search using a real-world road network dataset.

By evaluating multiple performance metrics across identical test cases, the project demonstrates how different search strategies behave when solving pathfinding problems on large graphs.

The experimental results can be used to understand the trade-offs between search time, memory usage, and node exploration.

---

**Project Category:** Artificial Intelligence  
**Programming Language:** C++17 and Python  
**Dataset:** Stanford SNAP roadNet-PA  
**Environment:** Google Colab / Local Machine
