# 🛍️ E-commerce Customer Segmentation & Purchasing Behavior

## 📌 Overview

This project analyzes e-commerce customer purchasing behavior and identifies distinct customer segments based on transaction characteristics.

The analysis covers data cleaning, exploratory data analysis, purchasing trends, customer segmentation using K-Means clustering, cohort analysis, product preferences, and statistical hypothesis testing.

The objective is to understand differences in purchasing behavior across segments and generate insights that can support targeted marketing and promotional strategies.

---

## 🎯 Business Objective

* Understand customer purchasing behavior.
* Analyze revenue and purchase trends over time.
* Segment transactions based on purchasing characteristics.
* Identify product preferences across customer segments.
* Analyze cohort purchasing behavior.
* Statistically test differences in order size between selected segments.
* Generate business recommendations for targeted promotions and customer engagement.

---

## 📂 Dataset

The project uses an e-commerce transaction dataset containing the following main variables:

* `InvoiceNo` — Transaction/invoice identifier
* `StockCode` — Product identifier
* `Description` — Product description
* `Quantity` — Number of products purchased
* `InvoiceDate` — Transaction date and time
* `UnitPrice` — Product unit price
* `CustomerID` — Customer identifier

Initial dataset size:

* **541,909 rows**
* **7 columns**

---

## 🛠️ Tools & Technologies

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* SciPy
* K-Means Clustering
* StandardScaler
* Exploratory Data Analysis
* Cohort Analysis
* Hypothesis Testing

---

## 🧹 Data Preparation

Several data preparation steps were performed before the analysis:

### Data Cleaning

* Converted `InvoiceDate` into datetime format.
* Renamed columns using `snake_case`.
* Removed **5,268 duplicate records**.
* Handled missing values in `description` and `customer_id`.
* Removed transactions without customer identification.
* Converted `customer_id` into string format.
* Removed non-product transactions such as `POST` (postage) and `M` (manual).
* Standardized product descriptions to lowercase.
* Cleaned inconsistent product descriptions.
* Removed unnecessary or damaged/missing product records.
* Converted negative quantities into positive values.
* Removed outliers from `quantity` and `unit_price`.

After preprocessing and outlier removal, the analytical dataset contained:

**339,645 rows and 9 columns.**

---

## 📊 Exploratory Data Analysis

### Revenue Trend

Revenue was calculated using:

```text
Revenue = Quantity × Unit Price
```

Daily revenue analysis showed an overall positive trend over the analyzed period, indicating increasing purchasing activity.

### Average Purchase

The analysis examined daily average purchase quantity to understand whether customers were purchasing larger quantities over time.

The notebook indicates that purchase volume remained relatively stable without major peaks, despite the positive revenue trend.

### Average Revenue per User

Monthly average revenue per user was analyzed to identify changes in customer purchasing activity.

The analysis showed a positive month-over-month trend in average revenue per user, suggesting increasing purchasing activity over time.

---

## 🤖 Customer Segmentation

K-Means clustering was used to identify groups with similar purchasing characteristics.

The clustering features were:

* `quantity`
* `unit_price`

Before clustering, the variables were standardized using `StandardScaler`.

The Elbow Method was evaluated across **2–10 clusters**, and the analysis selected:

**3 clusters**

### Cluster Profiles

| Cluster   | Avg. Quantity | Avg. Unit Price | Avg. Revenue |
| --------- | ------------: | --------------: | -----------: |
| Cluster 0 |          3.74 |            4.72 |        17.72 |
| Cluster 1 |          3.34 |            1.72 |         5.98 |
| Cluster 2 |         15.20 |            1.30 |        18.78 |

### Cluster Interpretation

**Cluster 0 — Higher Unit Price**

Customers/transactions in this segment have a relatively higher average unit price and moderate purchase quantities, resulting in relatively high revenue per transaction.

**Cluster 1 — Lower Value Purchases**

This segment has the lowest average quantity, unit price, and revenue, representing lower-value purchasing behavior.

**Cluster 2 — High-Quantity Purchases**

This segment purchases substantially larger quantities while having a lower average unit price. Despite the lower unit price, the high purchase quantity results in the highest average revenue among the three clusters.

---

## 📦 Product Preferences by Cluster

Product-level revenue was analyzed for each cluster to identify the products generating the highest revenue.

### Top Products

| Cluster   | Top Product by Revenue             |
| --------- | ---------------------------------- |
| Cluster 0 | Party Bunting                      |
| Cluster 1 | White Hanging Heart T-Light Holder |
| Cluster 2 | Jumbo Bag Red Retrospot            |

These differences indicate that product preferences vary across purchasing segments and can potentially be used to support targeted product recommendations and promotions.

---

## 📅 Cohort Analysis

Cohort analysis was performed based on customers' first purchase month.

The analysis created revenue-per-user cohort heatmaps for each cluster to examine purchasing behavior throughout the customer lifecycle.

One notable pattern was observed in the **November 2018 cohort**, which showed relatively higher revenue compared with other cohorts and peaked around the later stage of its lifecycle.

This suggests the presence of seasonal purchasing behavior and potential opportunities for repeat-purchase campaigns.

---

## 🧪 Hypothesis Testing

The project also tested whether average order quantity differed between Cluster 0 and Cluster 2.

### Hypotheses

**H₀:** The average order size of Cluster 0 and Cluster 2 is the same.

**H₁:** The average order size of Cluster 0 and Cluster 2 is different.

Significance level:

```text
α = 0.05
```

An independent two-sample t-test with unequal variance was applied.

### Result

The test produced:

```text
p-value = 0.0
```

Since the p-value is below the 5% significance level, the null hypothesis was rejected.

This provides statistical evidence that the average order quantity differs between Cluster 0 and Cluster 2.

---

## 💡 Key Findings

1. E-commerce purchasing behavior can be separated into **three distinct clusters** using quantity and unit price.
2. Cluster 1 represents relatively lower-value purchasing behavior.
3. Cluster 0 has the highest average unit price among the three segments.
4. Cluster 2 has substantially higher purchase quantities and the highest average revenue per transaction.
5. Product preferences differ across clusters.
6. Revenue and average revenue per user show positive trends over time.
7. Cohort analysis indicates periods with stronger purchasing activity and potential seasonal behavior.
8. Statistical testing indicates a significant difference in average order quantity between Cluster 0 and Cluster 2.

---

## 📈 Analytical Workflow

```text
Raw E-commerce Data
        ↓
Data Observation
        ↓
Data Cleaning & Preprocessing
        ↓
Missing Value & Duplicate Handling
        ↓
Outlier Treatment
        ↓
Revenue Calculation
        ↓
Exploratory Data Analysis
        ↓
Feature Standardization
        ↓
K-Means Clustering
        ↓
3 Customer Segments
        ↓
Cluster & Product Analysis
        ↓
Cohort Analysis
        ↓
Hypothesis Testing
        ↓
Business Insights & Recommendations
```

---

## 💼 Business Value

The analysis can support e-commerce businesses in:

* Developing segment-specific marketing campaigns.
* Creating targeted product recommendations.
* Identifying high-quantity purchasing segments.
* Designing promotions based on purchasing behavior.
* Identifying seasonal purchasing periods.
* Supporting customer retention and repeat-purchase strategies.
* Understanding differences in customer purchasing patterns through data-driven segmentation.

---

## 📁 Project Structure

```text
├── README.md
├── Customer_Segments.ipynb
└── dataset/
    └── ecommerce_dataset_us.csv
```

---

## 👤 Author

**I Putu Darma Ruswara**

Data Analyst | Business Analytics & Data Governance
