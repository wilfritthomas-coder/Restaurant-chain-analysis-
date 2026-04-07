# 🍽️ Restaurant Chain Analysis
### Identifying, Profiling & Benchmarking Restaurant Chains — Ratings & Popularity Study

---

## 📋 Project Overview

This project performs an end-to-end analytical investigation into restaurant chains present within a global restaurant dataset. The analysis identifies all multi-outlet brands, quantifies their market presence, benchmarks their ratings against standalone restaurants, and surfaces the highest-performing chains by various business-critical dimensions.

---

## 🗂️ Project Structure

```
restaurant_chain_analysis/
│
├── data/
│   └── dataset.csv                         # Source dataset (9,551 records, 21 features)
│
├── notebooks/
│   └── restaurant_chain_analysis.ipynb     # Full annotated Jupyter notebook
│
├── outputs/
│   ├── chain_summary.csv                   # Aggregated chain metrics table
│   ├── fig1_top15_chains_by_outlets.png    # Top 15 chains by outlet count
│   ├── fig2_rating_chains_vs_standalone.png# Rating distribution & boxplot comparison
│   ├── fig3_chain_popularity_bubble.png    # Bubble chart: outlets vs rating vs votes
│   ├── fig4_rating_category_breakdown.png  # Stacked bar: rating categories per chain
│   ├── fig5_geographic_spread.png          # Cities covered vs outlet count
│   ├── fig6_votes_analysis.png             # Total & average votes per chain
│   └── fig7_performance_heatmap.png        # Normalized multi-metric heatmap
│
├── README.md                               # This file
└── task_explanation.txt                    # Plain-language task summary
```

---

## 📊 Dataset Overview

| Attribute       | Value                        |
|----------------|------------------------------|
| Total Records  | 9,551                        |
| Total Features | 21                           |
| Key Fields     | Restaurant Name, City, Country Code, Cuisines, Aggregate Rating, Votes, Price Range |
| Rating Scale   | 0.0 – 4.9 (Aggregate Rating) |
| Rating Labels  | Excellent, Very Good, Good, Average, Poor, Not Rated |

---

## 🔍 Methodology

### Chain Identification Logic
A restaurant is classified as a **chain** when its name appears in **two or more distinct records** within the dataset. This mirrors standard food-service industry practice, where any brand operating multiple outlet locations qualifies as a chain entity.

### Metrics Computed per Chain
| Metric             | Description                                            |
|--------------------|--------------------------------------------------------|
| `outlet_count`     | Total number of outlet records in the dataset          |
| `avg_rating`       | Mean aggregate rating across all outlets               |
| `total_votes`      | Sum of all customer votes across outlets               |
| `avg_votes`        | Average votes per outlet (engagement per location)     |
| `cities_covered`   | Number of distinct cities the chain operates in        |
| `countries`        | Number of distinct countries the chain operates in     |
| `avg_cost`         | Mean average cost for two people                       |

---

## 📈 Key Findings

| Finding                             | Value        |
|------------------------------------|--------------|
| Total restaurant chains identified  | **734**      |
| Total chain outlet records          | **2,839**    |
| Chain share of dataset              | **29.7%**    |
| Standalone restaurants              | **6,712**    |
| Avg rating — Chains                 | **3.34**     |
| Avg rating — Standalone             | **3.49**     |
| Largest chain by outlet count       | **83 outlets**|
| Highest-rated chain (≥5 outlets)    | **Avg 4.58** |

### Notable Observations
- **Standalone restaurants** carry a marginally higher average rating (3.49 vs 3.34), suggesting that scale does not guarantee quality consistency.
- The **top chain** by outlet count leads significantly, with its nearest competitor trailing by several locations — indicating highly concentrated chain presence.
- The **highest-rated chains** (with meaningful outlet counts) maintain ratings above 4.3, placing them in the "Excellent" bracket — demonstrating that quality and scale can coexist.
- Chains with the **highest total votes** do not necessarily hold the highest ratings, revealing that popularity and quality are distinct dimensions.
- The majority of chain outlets (by the stacked analysis) fall in the **"Average"** rating category, pointing to a quality floor challenge across mid-tier chains.

---

## 🛠️ Dependencies

```
pandas
numpy
matplotlib
seaborn
```

Install via:
```bash
pip install pandas numpy matplotlib seaborn
```

---

## ▶️ How to Run

1. Ensure `data/dataset.csv` is present in the `data/` directory.
2. Open `notebooks/restaurant_chain_analysis.ipynb` in Jupyter Lab or Jupyter Notebook.
3. Run all cells sequentially (Kernel → Restart & Run All).
4. All output figures and the CSV summary will be generated in the `outputs/` directory.

---

## 📤 Outputs

| File                              | Type   | Description                                              |
|-----------------------------------|--------|----------------------------------------------------------|
| `chain_summary.csv`               | CSV    | Complete chain-level aggregated metrics for all 734 chains |
| `fig1_top15_chains_by_outlets`    | PNG    | Horizontal bar chart of top 15 chains by outlet count    |
| `fig2_rating_chains_vs_standalone`| PNG    | Histogram + boxplot comparing rating distributions       |
| `fig3_chain_popularity_bubble`    | PNG    | Bubble scatter: scale vs quality vs engagement           |
| `fig4_rating_category_breakdown`  | PNG    | Stacked bar: rating tier composition per top-10 chain    |
| `fig5_geographic_spread`          | PNG    | Cities covered and outlet count side-by-side             |
| `fig6_votes_analysis`             | PNG    | Total votes and per-outlet votes for top chains          |
| `fig7_performance_heatmap`        | PNG    | Normalized heatmap of all key metrics, top 15 chains     |

---

*Analysis conducted as part of an internship data analytics project.*
