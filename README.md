# Customer Segmentation Using K-Means Clustering

## Project Overview
This project applies K-Means Clustering, an unsupervised machine learning algorithm, to segment mall customers based on their annual income and spending score.
The objective is to identify meaningful customer groups and explore how businesses could use these insights to develop targeted marketing strategies.

## Dataset
**Dataset:** Mall Customers Dataset  
The dataset contains information about 200 customers with the following columns:
- **CustomerID:** Unique customer identifier
- **Genre:** Customer gender
- **Age:** Customer age
- **Annual Income (k$):** Annual income in thousands of dollars
- **Spending Score (1-100):** Customer spending score

**Features selected for clustering:**
- `Annual Income (k$)`
- `Spending Score (1-100)`

## Technologies Used
- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Joblib
- Jupyter Notebook

## Project Workflow
1. **Exploratory Data Analysis (EDA)**
   - Examined the dataset structure.
   - Checked for missing values and duplicate rows.
   - Analyzed feature distributions and relationships.
2. **Data Preprocessing**
   - Selected Annual Income and Spending Score.
   - Standardized the features using `StandardScaler`.
3. **K-Means Clustering**
   - Applied K-Means to identify customer groups.
   - Used `random_state=42` and `n_init=10`.
4. **Optimal Cluster Selection**
   - Evaluated cluster counts using the Elbow Method.
   - Compared Silhouette Scores for $K = 2$ to $10$.
   - Selected $K = 5$ based on the evaluation results.
5. **Cluster Visualization**
   - Visualized customer segments using a scatter plot.
   - Displayed cluster centroids in the original feature units.
6. **Model Saving**
   - Saved the trained K-Means model and fitted `StandardScaler` using Joblib.

## Model Performance

| Metric | Result |
| :--- | :--- |
| Number of customers | 200 |
| Selected number of clusters | 5 |
| Silhouette Score | 0.555 |
| Inertia | 65.57 |

## Customer Segments Identified

| Cluster | Customer Segment | Customers | Percentage |
| :---: | :--- | :---: | :---: |
| **0** | Average Income, Average Spending | 81 | 40.5% |
| **1** | High Income, High Spending | 39 | 19.5% |
| **2** | Low Income, High Spending | 22 | 11.0% |
| **3** | High Income, Low Spending | 35 | 17.5% |
| **4** | Low Income, Low Spending | 23 | 11.5% |

## Business Insights
- **Cluster 0:** The largest customer segment. Personalized offers could be explored to encourage engagement.
- **Cluster 1:** High-income, high-spending customers may be suitable for premium experiences and loyalty programs.
- **Cluster 2:** Low-income, high-spending customers could be considered for relevant rewards and promotions.
- **Cluster 3:** High-income, low-spending customers present an opportunity to investigate barriers to engagement.
- **Cluster 4:** Low-income, low-spending customers could be considered for value-focused promotions.

*These recommendations are exploratory and would require validation using additional customer behavior data.*

## Project Structure
```text
customer-segmentation/
├── data/
│   └── Mall_Customers.csv
├── models/
│   ├── kmeans_model.pkl
│   └── scaler.pkl
├── notebook/
│   └── customer_segmentation.ipynb
└── README.md