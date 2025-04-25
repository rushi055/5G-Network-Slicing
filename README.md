
---

# Network Slicing in 5G – Data-Driven Analysis  
### 2024GR07EC431

---

## Group Details:

- **Rushikesh Chaudhari** - 202251113  
- **Gopal Verma** - 202251173 
- **Kirtan Parikh** - 202251085
- **Yash Bhattad** - 202251162

---

## Overview

**Network Slicing** in 5G enables **virtualized, independent networks** tailored for specific applications like **Healthcare**, **Smart Cities**, and **Industrial IoT**. Each slice guarantees a unique Quality of Service (QoS) to meet diverse user and device needs under the same physical infrastructure. This project explores how different slices behave in terms of **packet loss**, **delay**, **bitrate**, and other metrics, using a comprehensive dataset.

This repository demonstrates a **data-driven workflow** to:

- Load and optimize a 5G Network Slicing dataset.
- Explore and visualize distributions in **Packet Loss Rate**, **Packet Delay**, and **Slice Types**.
- Conduct **correlation analysis**, **PCA (Principal Component Analysis)**, and **time-series analysis**.
- Evaluate **slice-based performance** for various applications (Healthcare, IoT, Public Safety).
- Export key plots for reporting purposes.

---

## Project Structure

```
5G_Slicing/
├── train_dataset.csv               # Raw dataset with slicing info
├── Network_Slicing_5G.ipynb        # Notebook with full EDA & analysis
└── results/                        # Output folder
    ├── correlation_matrix.png
    ├── slice_distribution.png
    ├── packet_loss_vs_delay.png
    ├── pca_visualization.png
    ├── slice_smartphone_stacked_bar.png
    └── outlier_boxplots/
        ├── packet_delay_boxplot.png
        ├── packet_loss_boxplot.png
        └── LTE_category_boxplot.png
```

---

## Dataset Description

| **Field**               | **Description**                                                         |
|-------------------------|-------------------------------------------------------------------------|
| **LTE/5G Category**     | Defines User Equipment performance category (1–22)                     |
| **Packet Loss Rate**    | Ratio of lost packets to total packets sent                             |
| **Packet Delay**        | Time for a packet to be received (in ms)                                |
| **Slice Type**          | 1 = eMBB, 2 = URLLC, 3 = mMTC (virtualized networks)                    |
| **GBR / Non-GBR**       | Guaranteed Bit Rate configurations                                      |
| **Applications**        | Flags for usage: Healthcare, Industry 4.0, IoT Devices, Smart City, etc.|
| **IoT**                 | Count of IoT devices in use                                             |
| **Smartphone**          | Usage for smartphone data                                               |

---

## Data Preprocessing

- **Memory Optimization**: Reduced memory usage by **86%** via data type optimization.
- **Renamed Columns** for ease of use (removed special characters).
- **No Null Values** detected; direct EDA was feasible.
- **Dimensionality Reduction** applied using **PCA** for visualization.

---

## Key Analysis Steps

1. **Exploratory Data Analysis (EDA)**:
   - **Histograms** & **Scatter Matrices** to understand distributions and relationships.
   - **Violin Plots** & **Boxplots** to assess variability and detect **outliers**.
   - **Correlation Heatmap** showing inter-dependencies among metrics.
   - **Slice Distribution** visualized through **bar** and **treemap** plots.

2. **Statistical Analysis**:
   - **Correlation** between **Packet Loss** and **Delay** observed.
   - **Group-wise Mean Analysis** of Packet Loss by Slice Type.
   - **Hexbin Plots** to assess density of loss vs. delay.
   - **Time-Series** resampling to track **Packet Loss** trends over time.

3. **Dimensionality Reduction**:
   - **PCA** applied to standardized metrics (excluding categorical variables).
   - Visualized key **principal components** to explore inherent structure.

4. **Categorical Analysis**:
   - **Stacked Bar Charts** for **Slice Type** usage by **Smartphone** presence.
   - Scatterplot Matrix to visualize **multiple variable relationships**.

---

## Visualization Highlights

- **Packet Loss Rate vs. Delay**: Visual correlation between reliability and latency.
- **Slice Type Distribution**: Slice 1 most dominant, followed by Slice 3 and Slice 2.
- **Correlation Matrix**: Strong/weak dependencies among numerical features.
- **Outlier Analysis**: Detected in Packet Delay and LTE Categories.
- **PCA Visualization**: Clear variance captured in first two components.
- **Treemap & Stacked Bars**: Slice-level contribution insights for packet metrics.

---

## Key Findings (Sample)

- **Slice 1** dominates the dataset (~53%) with moderate packet loss and delay.
- **Packet Delay** shows variability across LTE categories, indicating performance differences.
- **Packet Loss Rate** remains low overall but spikes in certain configurations.
- **Packet Loss** moderately correlates with **Packet Delay** (r ≈ 0.42).
- **Memory Optimization** significantly reduced computational load for large datasets.

---

## Next Steps

- **Predictive Modeling** for slice assignment based on real-time inputs.
- **Advanced Clustering** to identify underperforming slice configurations.
- **Deployment Simulations** to test slice efficacy in simulated environments.
- Explore **AutoViz** for deep auto-generated EDA reports.

---

## Installation & Tools

- **Python Libraries**: `pandas`, `numpy`, `matplotlib`, `seaborn`, `sklearn`, `squarify`, `AutoViz`.
- **Dataset Source**: Custom-generated, focusing on 5G slicing scenarios.
- **Memory Optimization**: Custom `reduce_mem_usage()` function.

---
