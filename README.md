# 🚚 Mini Courier Planner

<p align="center">
  <a href="https://github.com/HarshKamboj25/Mini-Courier-Planner">
    <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=25&duration=3000&pause=1000&color=38BDF8&center=true&vCenter=true&width=650&lines=Mini+Courier+Planner;Smart+Parcel+Selection;Optimized+Delivery+Routing;Algorithms+in+Action" alt="Animated Mini Courier Planner heading" />
  </a>
</p>

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

<p align="center">
  <a href="#-about-the-project">Overview</a> •
  <a href="#-system-workflow">Workflow</a> •
  <a href="#-project-results">Results</a> •
  <a href="#-performance-analysis">Performance</a> •
  <a href="#-getting-started">Run Project</a>
</p>

---

## 📌 About the Project

Mini Courier Planner is a Python-based courier optimization system developed as a Design and Analysis of Algorithms (DAA) capstone project.

It combines sorting, dynamic programming, graph algorithms, and approximation techniques to solve two major courier-planning challenges:

- **📦 Parcel Optimization:** Select the most valuable combination of parcels without exceeding vehicle capacity.
- **🗺️ Delivery Optimization:** Determine an efficient customer visit order using shortest-path calculations and route planning.

The system transforms parcel and route datasets into a complete delivery plan, followed by empirical runtime evaluation.

---

## ⚡ System Workflow

The complete pipeline takes the system from raw input datasets to an optimized parcel selection and delivery route.

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

### 🔄 Algorithmic Pipeline

| Stage | Algorithm | Responsibility |
|---|---|---|
| 01 | ⚡ Merge Sort | Parcel prioritization using priority and deadlines |
| 02 | 🎒 0/1 Knapsack DP | Maximum-value parcel selection within capacity |
| 03 | 📍 Dijkstra | Shortest paths through the weighted graph |
| 04 | 🚚 Nearest-Neighbor TSP | Approximate customer delivery tour |
| 05 | ⏱️ Runtime Analysis | Performance evaluation across input sizes |

<details>
<summary><strong>🧠 Explore the algorithmic implementation</strong></summary>

### 1. Parcel Prioritization

Merge Sort arranges parcels in descending order of priority. When priorities are equal, parcels with earlier deadlines are placed first.

### 2. Capacity Optimization

The 0/1 Knapsack algorithm uses Dynamic Programming to select parcels while respecting the vehicle's maximum carrying capacity.

### 3. Shortest-Path Computation

Dijkstra's Algorithm calculates minimum travel distances between the warehouse and delivery locations using a weighted graph.

### 4. Delivery Tour Construction

The Nearest-Neighbor TSP heuristic selects the next closest unvisited customer and constructs a complete delivery tour, including the return to the warehouse.

### 5. Performance Evaluation

Execution times are measured for increasing input sizes to study the computational behaviour of the implemented algorithms.

</details>

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

## 🛣️ Route Visualization

The project generates a visual representation of the final delivery route across the weighted delivery network.

<p align="center">
  <img src="images/route_visualization.png" width="85%" alt="Mini Courier Planner delivery route visualization" />
  <br>
  <sub>Generated delivery route visualization.</sub>
</p>

---

## 🚀 Getting Started

Follow these steps to run the project locally.

### 1. Clone the Repository

```bash
git clone https://github.com/HarshKamboj25/Mini-Courier-Planner.git
cd Mini-Courier-Planner
```

### 2. Create a Virtual Environment (Optional)

**Windows**

```bash
python -m venv .venv
.venv\Scripts\activate
```

**Linux / macOS**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook mini_courier_planner.ipynb
```

### 5. Run the Pipeline

Execute the notebook cells sequentially to reproduce:

- Parcel prioritization
- Optimal parcel selection
- Shortest-path calculations
- Delivery route construction
- Runtime benchmarking and visualizations

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
| **Total Route Distance** | **29 km** |

### 🚚 Final Delivery Traversal

```text
Warehouse
    ↓
    B → C → D → E
              ↓
Warehouse ← A ← C ← D
```

**Expanded Shortest-Path Traversal:**

```text
Warehouse → B → C → D → E → D → C → A → Warehouse
```

The Nearest-Neighbor TSP heuristic determines the customer visit order, while Dijkstra's Algorithm provides the shortest physical paths between consecutive locations.

---

## 📊 Performance Analysis

The four major algorithmic components were benchmarked using increasing input sizes:

<p align="center">
  <img src="https://img.shields.io/badge/Input%20Sizes-10%20%7C%2025%20%7C%2050%20%7C%20100%20%7C%20200-2563EB?style=for-the-badge" />
</p>

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

> **Key Observation:** The Nearest-Neighbor TSP component becomes the dominant computational bottleneck as the tested input size increases.

---

## 🛠️ Technology Stack

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white" />
  <img src="https://img.shields.io/badge/NetworkX-333333?style=flat-square" />
  <img src="https://img.shields.io/badge/Matplotlib-11557C?style=flat-square" />
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white" />
  <img src="https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white" />
</p>

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

## 👨‍💻 Author

**Harsh Kamboj**

---

<p align="center">
  <strong>🚚 Mini Courier Planner</strong><br>
  <em>Prioritize. Optimize. Deliver.</em><br><br>
  Built with Python and Algorithmic Thinking.
</p>

<p align="center">
  <a href="#-mini-courier-planner">⬆ Back to Top</a>
</p>
