# 🚚 Mini Courier Planner

<p align="center">
  <strong>From Parcel Selection to Route Optimization</strong><br>
  An Algorithm-Driven Courier Planning System
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Algorithms-DAA-orange" />
  <img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white" />
  <img src="https://img.shields.io/badge/Status-Completed-success" />
</p>

---

## 🎓 Project Information

| Detail | Information |
|---|---|
| **Project Title** | Mini Courier Planner |
| **Author** | Harsh Kamboj |
| **Roll Number** | 2501730059 |
| **Programme** | B.Tech CSE (AI & ML) |
| **Course** | Design and Analysis of Algorithms |
| **Institution** | K.R. Mangalam University |

---

## 📌 About the Project

Mini Courier Planner is a Python-based courier optimization system developed as a DAA capstone project.

It combines fundamental algorithmic techniques to solve two major courier-planning challenges:

- **Parcel Optimization:** Which parcels should be selected to maximize total value without exceeding vehicle capacity?
- **Delivery Optimization:** In what order should delivery locations be visited to reduce the overall travel distance?

The system integrates sorting, dynamic programming, graph algorithms, and approximation techniques into one complete planning workflow.

---

## ⚡ How the System Works

The project follows a sequential algorithmic pipeline, from raw input data to the final delivery plan.

```mermaid
flowchart TD
    A(["📦 Parcel & Route Data"]) --> B["📥 Load Input Datasets"]
    B --> C["⚡ Merge Sort<br/>Parcel Prioritization"]
    C --> D["🎒 0/1 Knapsack DP<br/>Capacity Optimization"]
    D --> E["✅ Selected Parcels"]
    E --> F["📍 Extract Delivery Destinations"]
    F --> G["🗺️ Weighted Delivery Graph"]
    G --> H["🔎 Dijkstra's Algorithm<br/>Shortest Paths"]
    H --> I["🚚 Nearest-Neighbor TSP<br/>Delivery Tour Planning"]
    I --> J["🏁 Final Route & Total Distance"]
    J --> K["📊 Runtime Analysis"]
    K --> L(["📈 Performance Evaluation"])

    style A fill:#17324d,stroke:#60a5fa,color:#fff
    style E fill:#14532d,stroke:#4ade80,color:#fff
    style J fill:#14532d,stroke:#4ade80,color:#fff
    style L fill:#312e81,stroke:#a5b4fc,color:#fff
```

### 🔄 Algorithmic Workflow

| Stage | Technique | Purpose |
|---|---|---|
| 01 | **Merge Sort** | Prioritizes parcels using priority and delivery deadlines |
| 02 | **0/1 Knapsack (DP)** | Selects the maximum-value feasible parcel combination |
| 03 | **Dijkstra's Algorithm** | Computes shortest paths in the weighted delivery graph |
| 04 | **Nearest-Neighbor TSP** | Constructs an approximate delivery tour |
| 05 | **Runtime Analysis** | Evaluates algorithm performance across different input sizes |

---

## 🧠 Core Algorithm Design

**1. Parcel Prioritization**

Merge Sort arranges parcels in descending order of priority. When priorities are equal, parcels with earlier deadlines are placed first.

**2. Capacity Optimization**

The 0/1 Knapsack algorithm uses Dynamic Programming to select parcels while respecting the vehicle's maximum carrying capacity.

**3. Shortest-Path Computation**

Dijkstra's Algorithm calculates minimum travel distances between the warehouse and delivery locations using a weighted graph.

**4. Delivery Tour Construction**

The Nearest-Neighbor TSP heuristic determines the next closest unvisited customer and builds a complete delivery tour, including the return to the warehouse.

**5. Performance Evaluation**

Execution times are measured for increasing input sizes to study the computational behaviour of the implemented algorithms.

---

## 📁 Repository Structure

```text
Mini-Courier-Planner/
│
├── datasets/
│   ├── parcels.csv
│   └── routes.csv
│
├── images/
│   ├── performance_results.csv
│   ├── route_visualization.png
│   └── runtime_chart.png
│
├── src/
│   ├── sorting.py
│   ├── knapsack.py
│   ├── dijkstra.py
│   ├── tsp.py
│   └── performance.py
│
├── mini_courier_planner.ipynb
├── requirements.txt
├── .gitignore
└── README.md
```

---

## 🚀 Getting Started

Follow these steps to run the project locally.

**1. Clone the repository**

```bash
git clone https://github.com/HarshKamboj25/Mini-Courier-Planner.git
cd Mini-Courier-Planner
```

**2. Create and activate a virtual environment (optional)**

Windows:

```bash
python -m venv .venv
.venv\Scripts\activate
```

Linux / macOS:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

**3. Install dependencies**

```bash
pip install -r requirements.txt
```

**4. Launch Jupyter Notebook**

```bash
jupyter notebook mini_courier_planner.ipynb
```

**5. Execute the notebook**

Run the notebook cells sequentially to reproduce parcel prioritization, optimal selection, shortest-path calculations, route construction, and performance analysis.

---

## 🏁 Project Results

The implemented system produces the following results for the supplied dataset:

| Metric | Result |
|---|---|
| Total Input Parcels | 15 |
| Vehicle Capacity | 15 kg |
| Selected Parcels | P04, P12, P05, P02 |
| Total Selected Weight | 15 kg |
| Total Parcel Value | 390 |
| Customer Visit Order | Warehouse → B → C → D → E → Warehouse |
| Total Route Distance | **29 km** |

### 🛣️ Final Delivery Route

```text
Warehouse → B → C → D → E → D → C → A → Warehouse
```

The customer visit order is generated by the Nearest-Neighbor TSP heuristic, while Dijkstra's Algorithm provides the shortest physical paths between consecutive delivery locations.

---

## 📊 Performance Analysis

The four major algorithmic components were benchmarked using increasing input sizes:

**N = 10, 25, 50, 100, 200**

### 📋 Performance Results

The measured execution times are stored in:

`images/performance_results.csv`

<p align="center">
  <img width="100%" alt="Performance Results Evidence" src="https://github.com/user-attachments/assets/42ba8fcf-f129-4569-91c0-8c0a50ca8109" />
  <br>
  <strong>Figure 1. Performance Results Evidence</strong>
  <br>
  <sub>Individual runtime measurements for the implemented algorithms.</sub>
</p>

### 📈 Runtime Comparison

<p align="center">
  <img width="100%" alt="Algorithm Runtime Comparison Chart" src="https://github.com/user-attachments/assets/4eea6241-b0c6-4ce0-a13e-d02f4ca5cbe9" />
  <br>
  <strong>Figure 2. Algorithm Runtime Comparison</strong>
  <br>
  <sub>Execution time comparison across different input sizes.</sub>
</p>

**Key Observation:** The Nearest-Neighbor TSP component becomes the dominant computational bottleneck as the tested input size increases.

---

## 🛠️ Technology Stack

| Technology | Application |
|---|---|
| **Python 3** | Core implementation |
| **Pandas** | Dataset handling and result tables |
| **NetworkX** | Weighted graph representation |
| **Matplotlib** | Route and performance visualization |
| **Jupyter Notebook** | Interactive execution and analysis |
| **Git & GitHub** | Version control and project hosting |

---

## 🔮 Future Enhancements

- 🚛 Multi-vehicle and multi-trip delivery planning
- ⚡ Shortest-path caching for improved efficiency
- 📅 Deadline-aware parcel selection
- 🧭 Comparison with advanced TSP heuristics
- 🌍 Evaluation using larger real-world delivery networks
- 🖥️ Interactive courier-planning dashboard

---

## 📚 Academic Context

This project demonstrates the practical application of **Design and Analysis of Algorithms (DAA)** concepts through an integrated courier-planning problem.

It brings together sorting, dynamic programming, graph traversal, approximation algorithms, and empirical performance evaluation in a single Python-based implementation.

<p align="center">
  <strong>Mini Courier Planner</strong><br>
  Designed and developed as a B.Tech CSE (AI & ML) DAA Capstone Project<br>
  K.R. Mangalam University
</p>
