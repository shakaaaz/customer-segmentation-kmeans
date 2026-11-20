# Mall Customer Segmentation with K-Means Clustering

Grouping 200 mall customers by income and spending behavior with K-Means (Python, scikit-learn), then turning each group into a business persona with marketing recommendations.

## Background

A shopping mall has basic customer data, but its marketing team has no structured customer grouping, so promotions remain generic. This project aims to:

- Identify distinct customer segments based on shopping behavior.
- Propose more targeted marketing strategies for each segment.

## Dataset

[Mall Customer Segmentation Data (Kaggle)](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python), containing 200 customers and 5 columns:

| Column | Description |
| :--- | :--- |
| `CustomerID` | Customer ID (not used in modeling) |
| `Gender` | Male / Female |
| `Age` | Customer age |
| `Annual Income (k$)` | Annual income in thousands of dollars |
| `Spending Score (1-100)` | Spending score assigned by the mall |

The data is clean: no missing values and no duplicate rows.

## Methodology

1. **Data understanding:** check structure, missing values, and duplicates.
2. **EDA:** univariate and bivariate analysis (histograms, scatter plot, pairplot, correlation heatmap).
3. **Preprocessing:** select `Annual Income` and `Spending Score`, then standardize with `StandardScaler`.
4. **Choosing the number of clusters:** Elbow Method and Silhouette Score for K = 2 to 10.
5. **Clustering and profiling:** K-Means with K = 5, then interpret each cluster.

## Key Results

The highest Silhouette Score is at **K = 5 (0.5547)**, consistent with the "elbow" in the Elbow Method.


| Segment | Avg. Income (k$) | Avg. Spending Score | Avg. Age | Customers |
| :--- | ---: | ---: | ---: | ---: |
| Premium Customers | 86.5 | 82.1 | 32.7 | 39 |
| Selective High-Earners | 88.2 | 17.1 | 41.1 | 35 |
| Enthusiastic Spenders | 25.7 | 79.4 | 25.3 | 22 |
| Budget-Conscious | 26.3 | 20.9 | 45.2 | 23 |
| Mainstream Customers | 55.3 | 49.5 | 42.7 | 81 |

Highlights:

- The largest segment is **Mainstream Customers** (81 of 200 customers).
- **Selective High-Earners** have high income but low spending, making them a promising target for dedicated campaigns.
- Although age was not used for clustering, average age differs across segments: **Enthusiastic Spenders** are the youngest (about 25) and **Budget-Conscious** customers the oldest (about 45).
- Gender composition is fairly balanced across all segments, so gender is not a strong differentiator.

## Marketing Recommendations (hypotheses to test)

| Segment | Strategy ideas |
| :--- | :--- |
| Premium Customers | VIP loyalty program, early access to new products, exclusive experiences. |
| Selective High-Earners | Messaging focused on quality and value, bundles of high-value products. |
| Enthusiastic Spenders | Flash sales, trend-based promotions, loyalty points program. |
| Budget-Conscious | Affordable promotions and cashback on everyday items. |
| Mainstream Customers | Shopping vouchers and seasonal events to keep visits regular. |

These recommendations are hypotheses based on segment profiles, not tested results. Their effectiveness should be validated, for example through A/B testing.

## Limitations

- Small sample size (200 customers).
- `Spending Score` is assigned by the mall, not derived from real transaction data.
- Clustering uses only two features, so other factors such as age and product category are not considered.
- This is a widely used practice dataset, so results may not reflect real business conditions.

## Future Work

- Include `Age` in the clustering features.
- Compare with other algorithms (e.g., Hierarchical Clustering or DBSCAN).
- Test cluster stability using different `random_state` values.

## How to Run

```bash
git clone https://github.com/USERNAME/REPO-NAME.git](https://github.com/shakaaaz/customer-segmentation-kmeans
cd customer-segmentation-kmeans
pip install -r requirements.txt
jupyter notebook customer_segmentation.ipynb
```

## Tools

Python, pandas, NumPy, matplotlib, seaborn, scikit-learn

## Repository Structure

```
├── customer_segmentation.ipynb
├── Mall_Customers.csv
├── requirements.txt
└── README.md
```
