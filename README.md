# SmartCart Customer Segmentation 🛒

### Customer Segmentation using Unsupervised Machine Learning

SmartCart Customer Segmentation is a machine learning project focused on identifying groups of customers with similar characteristics and purchasing behaviour. The project uses customer demographics, income, spending patterns, purchase channels, and campaign responses to understand different customer segments.

The main goal is to explore customer data and discover useful patterns that can help businesses understand their customers and plan more targeted marketing strategies.

## 📌 Project Overview

This project follows an end-to-end customer segmentation workflow, starting with data cleaning and exploratory data analysis and ending with clustering and business interpretation.

I used two clustering algorithms, K-Means and Agglomerative Clustering, to group customers and compared their characteristics to understand how the segments differ.

## 📂 Dataset

- **Dataset:** `smartcart_customers.csv`
- **Original dataset size:** 2,240 rows and 22 columns
- **Records after cleaning:** 2,236 customers
- **Missing values:** 24 entries in the `Income` column

The dataset contains information about customer income, education, household details, product spending, purchasing channels, and campaign responses.

## 🛠️ Technologies Used

- Python
- Jupyter Notebook
- Pandas and NumPy
- Matplotlib and Seaborn
- Scikit-learn

## ⚙️ Project Workflow

### 1. Data Loading and Cleaning
Loaded the dataset into Pandas, explored its structure, and handled missing income values using median imputation.

### 2. Feature Engineering
Created new features to make customer behaviour easier to analyse:

- `Age` — calculated from the birth year.
- `Customer_Tenure_Days` — represents the difference between a customer's joining date and the latest joining date in the dataset.
- `Total_Spending` — combines spending across six product categories.
- `Total_Children` — combines the number of children and teenagers in the household.

### 3. Data Preparation
Simplified education and household categories, removed redundant columns, and filtered records using age and income thresholds. The resulting cleaned dataset contained 2,236 customers.

### 4. Exploratory Data Analysis (EDA)
Used pair plots, correlation analysis, and a heatmap to explore feature distributions and relationships between customer attributes.

### 5. Encoding and Feature Scaling
Applied One-Hot Encoding to categorical features and StandardScaler to standardise numerical values before clustering.

The resulting feature matrix contained **2,236 customers and 18 features**.

### 6. Principal Component Analysis (PCA)
Reduced the 18-dimensional feature matrix to three principal components for visualisation.

The three components retained approximately **44.95% of the total variance**, allowing the customer groups to be displayed in a 3D plot while losing some information from the original data.

### 7. Selecting the Number of Clusters
Used the Elbow Method and Silhouette Score to investigate suitable cluster counts. The saved Elbow Method output suggested four clusters.

### 8. Customer Clustering
Applied two unsupervised learning algorithms:

- **K-Means:** Groups customers around cluster centroids.
- **Agglomerative Clustering:** Builds customer groups by progressively merging similar clusters using Ward linkage.

Both algorithms were configured to produce four clusters and visualised in PCA space.

### 9. Cluster Analysis
Used cluster-size plots, income-versus-spending visualisations, and average feature values to understand the characteristics of each customer group.

## 🤖 Algorithms and Techniques

- K-Means Clustering
- Agglomerative Clustering
- Principal Component Analysis (PCA)
- One-Hot Encoding
- StandardScaler
- Exploratory Data Analysis
- Feature Engineering

## 📊 Key Findings

The cluster summary showed differences in average income, spending, and purchasing behaviour.

| Cluster | Average Income | Average Spending | General Observation |
|---|---:|---:|---|
| 0 | 39,681 | 222 | Lower income and spending |
| 1 | 72,808 | 1,237 | High income and highest average spending |
| 2 | 36,960 | 166 | Lowest average income and spending |
| 3 | 70,723 | 1,190 | High income and spending |

*Income and spending values are reported in the dataset's original units.*

These results suggest that the customers can be divided into groups with different spending levels and purchasing patterns. Such segments could help businesses explore strategies for customer engagement, product recommendations, and targeted campaigns.

The cluster labels are algorithm-generated identifiers; they do not represent a ranking of customers or their business value.

## 📚 Key Learnings

Through this project, I gained practical experience in:

- Cleaning and preparing customer data.
- Creating meaningful features from existing columns.
- Exploring relationships through data visualisation.
- Applying PCA for dimensionality reduction.
- Understanding and implementing clustering algorithms.
- Interpreting cluster summaries from a business perspective.

One important takeaway is that clustering is an exploratory technique. The usefulness of the resulting segments depends on how well they represent meaningful differences in customer behaviour.

## 🔮 Future Improvements

- Compare clustering quality using numerical Silhouette Scores.
- Evaluate clustering on the original scaled features as well as PCA-transformed features.
- Compare K-Means and Agglomerative Clustering more systematically.
- Improve cluster interpretation using additional visualisations.
- Build an interactive dashboard to explore customer segments.

## ⚠️ Note

This project is intended for educational purposes and exploratory customer analysis. The identified clusters are not guaranteed to represent fixed customer types and should be validated before being used for business decisions.

## 👨‍💻 Author

**Anubhav Prakash**

B.Tech Computer Science and Engineering Student

Interested in Artificial Intelligence, Machine Learning, and Data Science.
