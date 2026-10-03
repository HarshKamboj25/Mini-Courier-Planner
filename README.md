# 🚚 Mini-Courier Planner

## Project Overview

Mini-Courier Planner is a Python-based courier planning system that prioritizes parcels, selects an optimal set of parcels within vehicle capacity, finds shortest delivery paths, and generates a delivery route.

## Algorithms Used

- Merge Sort – Parcel prioritization
- 0/1 Knapsack (Dynamic Programming)** – Optimal parcel selection
- Dijkstra's Algorithm – Shortest paths
- Nearest-Neighbor TSP – Delivery route planning
- Runtime Analysis – Performance evaluation

## Project Flow

   text
Parcel Data
    ↓
Sorting
    ↓
0/1 Knapsack
    ↓
Selected Parcels
    ↓
Dijkstra
    ↓
Nearest-Neighbor TSP
    ↓
Final Delivery Route
    ↓
Runtime Analysis

Dataset
- datasets/parcels.csv – Parcel information
- datasets/routes.csv – Weighted delivery graph

Project Structure

Mini-Courier-Planner/
├── datasets/
│   ├── parcels.csv
│   └── routes.csv
├── images/
│   ├── performance_results.csv
│   └── runtime_chart.png
├── src/
│   ├── sorting.py
│   ├── knapsack.py
│   ├── dijkstra.py
│   ├── tsp.py
│   └── performance.py
├── mini_courier_planner.ipynb
├── README.md
├── requirements.txt
└── .gitignore

Execution
Install the required dependencies:

pip install -r requirements.txt

Open and run:

mini_courier_planner.ipynb

Performance Analysis
The system was tested with different input sizes and runtime results were recorded and visualized in:
images/performance_results.csv
images/runtime_chart.png
Final Result
The system provides:
- Prioritized parcels
- Optimized parcel selection
- Shortest delivery paths
- Final delivery route
- Total route distance
- Runtime comparison
Technologies
Python, Pandas, NetworkX, Matplotlib, and Jupyter Notebook.