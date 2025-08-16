![R](https://img.shields.io/badge/Language-R-blue)
![Data Analysis](https://img.shields.io/badge/Domain-Distributed%20Data%20Analysis-orange)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

# Distributed Data Analysis & Fare Prediction on NYC Taxi Data

**R • Python • Parallel Computing**
Performance analysis and predictive modelling of large-scale taxi trip data using distributed computing techniques.

---

## 📚 Table of Contents

* [Overview](#overview)
* [Objectives](#objectives)
* [Dataset](#dataset)
* [Tools & Technologies](#tools--technologies)
* [Analysis & Results](#analysis--results)
* [Model Performance](#model-performance)
* [Insights](#insights)
* [File Structure](#file-structure)
* [How to Run](#how-to-run)
* [Author](#author)

---

## Overview

This project applies **distributed data analysis** techniques in **R** and **Python** to process and analyse a large taxi trips dataset efficiently. The work focuses on improving runtime through parallelisation, testing scalability in a high-performance computing (HPC) environment, and building predictive models for trip fare estimation.

---

## Objectives

1. Efficiently process a large taxi dataset using parallel and distributed computing.
2. Compare single-core vs multi-core execution performance.
3. Build and evaluate machine learning models for fare prediction.
4. Assess scalability and overhead trade-offs in HPC settings.

---

## Dataset

* **Dataset**: [NYC Yellow Taxi Trip Records – Kaggle](https://www.kaggle.com/datasets/elemento/nyc-yellow-taxi-trip-data) (public dataset)
* **Size**: Millions of trip records with columns such as:

  * Pickup and drop-off datetime/location
  * Trip distance and duration
  * Fare amount, tip amount, total amount
  * Passenger count
* Dataset is split into chunks for distributed processing across multiple cores/nodes.

---

## Tools & Technologies

* **R** – `parallel`, `doParallel`, `foreach` for multi-core computation.
* **Python** – Multiprocessing and HPC job execution.
* **HPC Cluster** – For large-scale distributed workloads.
* **Machine Learning** – Linear Regression, Random Forest, Gradient Boosting.
* **R Markdown** (`.Rmd`) – For detailed analysis documentation.

---

## Analysis & Results

### Parallel Processing in R

* Implemented `foreach` loops to process taxi data in parallel.
* Aggregated total fares, trip distances, and trip counts.
* **Result**: Up to **3.5x speed-up** on 4-core processing compared to single-core.

### Distributed Computing Benchmarks

* Tested on 1 million, 5 million, and 10 million trip records.
* Larger datasets benefited more from parallelisation until memory overhead reduced efficiency.

### Python HPC Integration

* HPC jobs executed for calculating trip-level statistics and aggregations.
* Compared local multiprocessing vs HPC execution.
* **Result**: HPC jobs processed the largest dataset **70% faster** than local multiprocessing.

### Scalability Testing

* Speed-up observed up to \~8 cores; diminishing returns beyond due to communication and memory transfer overhead.
* Optimal configuration found at 4–8 cores for balanced performance.

---

## Model Performance

Models were trained to predict taxi fares based on trip distance, time, passenger count, and pickup/drop-off locations.

| Model                   | RMSE | R²   | Notes                                                |
| ----------------------- | ---- | ---- | ---------------------------------------------------- |
| Linear Regression       | 5.82 | 0.89 | Fast baseline model                                  |
| Random Forest Regressor | 3.97 | 0.94 | Best overall accuracy, slightly higher training time |
| Gradient Boosting       | 4.10 | 0.93 | Competitive accuracy, efficient for medium datasets  |

**Key Findings:**

* Random Forest provided the best performance in terms of RMSE and R².
* Distributed processing reduced feature engineering and training times significantly for large datasets.
* Models generalised well with minimal overfitting observed.

---

## Insights

* Parallel processing significantly reduces runtime for both data preparation and model training.
* Performance gains plateau after a certain number of cores, highlighting overhead costs.
* Random Forest achieved the best trade-off between accuracy and runtime.
* Combining R for aggregation and Python for machine learning maximised efficiency.

---

## File Structure

```bash
distributed_data_analysis/
│
├── Distributed Data Analysis Coursework.Rmd   # R Markdown analysis
├── HPCI_DDA.ipynb                             # Python HPC integration & modelling
├── dataset/                                   # Taxi trip data files
└── README.md                                  # Project documentation
```

---

## How to Run

**R Markdown:**

1. Open `Distributed Data Analysis Coursework.Rmd` in RStudio.
2. Knit to HTML or PDF to generate the analysis report.

**Python Notebook:**

1. Open `HPCI_DDA.ipynb` in Jupyter Notebook or JupyterLab.
2. Run all cells to reproduce HPC experiments and ML results.

---

## Author

**Rakshitha Kamarathi Venkatesh**
📧 Email: [rakshitha0897@gmail.com](mailto:rakshitha0897@gmail.com)
🔗 [LinkedIn](https://www.linkedin.com/in/rakshitha-venkatesh-6824b7306/)
