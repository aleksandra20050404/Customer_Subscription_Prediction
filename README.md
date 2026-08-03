# Bank Marketing Campaign - Customer Subscription Prediction
---

##### A comprehensive machine learning project that predicts whether a bank client will subscribe to a term deposit based on marketing campaign data. The project implements a complete end-to-end ML pipeline including data preprocessing, exploratory data analysis, feature engineering, model training, and performance evaluation.

## Author

**Aleksandra Vislova**  

[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0072b1?&style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/aleksandra-vislova-a51ba9297)

---

## Files in This Repository

Bank-Marketing-Campaign-Prediction/
│
├── notebooks/
│   ├── EDA.ipynb              # Exploratory Data Analysis & Preprocessing
│   └── models.ipynb           # Model Training & Evaluation
│
├── data/
│   ├── X_train_encoded.csv    # Encoded training features
│   ├── X_test_encoded.csv     # Encoded test features
│   ├── y_train.csv            # Training labels
│   └── y_test.csv             # Test labels
│
├── models/
│   ├── best_model.pkl         # Trained Random Forest model
│   ├── preprocessor.pkl       # Data preprocessing pipeline
│   ├── label_encoder.pkl      # Label encoder for target variable
│   └── feature_names.pkl      # Feature names for prediction
│
├── outputs/
│   ├── feature_importance_report.csv  # Feature importance analysis
│   ├── model_performance.csv          # Model performance metrics
│   └── confusion_matrix.png           # Confusion matrix visualization
│
├── requirements.txt            # Project dependencies
├── README.md                  # Project documentation
└── LICENSE                    # License file
---


## Table of Contents

- [Project Background](#project-background)
- [Data Sources](#data-sources)
- [Technical Implementation](#technical-implementation)
- [ Model Training & Evaluation](#model-training-and-evaluation--findings)
- [Recommendations](#recommendations)
- [Summary](#summary)


---

## Project Background

This dataset contains data from direct telemarketing campaigns conducted by a Portuguese banking institution. The goal of the campaigns was to promote term deposit subscriptions. It includes a mix of client information, contact details, and campaign-specific attributes, making it classification tasks in marketing and financial analytics.​

### Business Objective
Help banking institution optimize their marketing campaigns by:
- Identifying high-potential customers who are most likely to subscribe to term deposits
- Reducing marketing costs by targeting the right customers
- Increasing conversion rates through data-driven decision making

Understanding key drivers of customer subscription behavior
## Data Sources

| Source | Description |
|--------|-------------|
| **UCI Machine Learning Repository** | Bank Marketing Data set was downloaded from UCI Machine Learning Repository: |
| **Data Link** | [Download Dataset](https://www.openml.org/search?type=data&status=active&id=43718) |
| **Records** |  11,162  records |
Instances: 11,162 ​

Features: 17 input variables + 1 output (y) ​

Target: y – whether the client subscribed to a term deposit (yes or no)​

---

### Calculated Fields Created in Looker Studio

| Calculated Field | Formula | Purpose |
|------------------|---------|---------|
| **Total Sales** | `Quantity * UnitPrice` | Calculates revenue per transaction line |
| **Order Count** | `COUNT_DISTINCT(InvoiceNo)` | Counts unique orders for frequency analysis |
| **Average Order Value (AOV)** | `SUM(TotalSales) / COUNT_DISTINCT(InvoiceNo)` | Measures average spend per order |
---

##  Technical Implementation

### Data Preprocessing Pipeline

![Sales by Country Map](https://github.com/aleksandra20050404/Online_Retail_Sales_Dashboard_Looker_Studio/blob/46b2b7217f59756595d981af899b42a12929dc29/img/table.jpg)

| Country | Total Sales | % of Total Revenue |
|---------|-------------|---------------------|
| United Kingdom | £8.18M | 84.0% |
| Netherlands | £285K | 2.9% |
| EIRE (Ireland) | £265K | 2.7% |
| Germany | £229K | 2.4% |
| France | £210K | 2.2% |
| Other Countries | £578K | 5.8% |

**Key Insight:** The UKis the dominant market (84% of revenue). Heavy reliance on a single country poses a concentration risk if market conditions change.

### 2. Product Sales by Country – Regional Preferences

#### UK Top Products:
Volume-led market anchored by DOTCOM POSTAGE, REGENCY CAKESTAND, WHITE HANGING HEART T-LIGHT HOLDER | 

![Top_10_Product](https://github.com/aleksandra20050404/Online_Retail_Sales_Dashboard_Looker_Studio/blob/46b2b7217f59756595d981af899b42a12929dc29/img/top_10_products.jpg)


#### Highest non-UK sales volumes (B2B/wholesale opportunity):

![Top_Countries_Products](https://github.com/aleksandra20050404/Online_Retail_Sales_Dashboard_Looker_Studio/blob/4193eeeb7b5765df806a2aee93cef03bca8329a9/img/top_countries_products.jpg)

Postage emerges as the top product across all three international markets (EIRE, Germany, and France), contributing over £350,000 in revenue to the store. While this indicates strong international demand, other products must be considered for inventory planning and promotions in Non-UK markets: 


| Total Sales (£) | Product Name | 
|----------------|------------|
| £21,000| Regency Cakestand |
| £11,000 | Rabbit Night Light | 
| £5,000| Round Snack Boxes | 


### 3. Average Order Value (AOV) by Country

![Average Order Value by Country](https://github.com/aleksandra20050404/Online_Retail_Sales_Dashboard_Looker_Studio/blob/46b2b7217f59756595d981af899b42a12929dc29/img/avg_order_value.jpg)

**Key Insight:** 
- Top AOV Market: Netherlands (£3,000,000 avg order)
- 2nd Highest: Australia (£2,400,000)
- 3rd Highest: 	Japan (£1,850,000)

---

## Recommendations

### Market Expansion

| Priority | Country | Action |
|----------|---------|--------|
| **1** | United Kingdom | Maintain as anchor market but monitor concentration risk (84% of total sales) |
| **2** | Netherlands, EIRE, Germany | Prioritize for expansion – already contribute meaningful sales (£284K, £263K, £222K respectively) |
| **3** | Australia, Japan | Dedicate B2B sales team managers to nurture high-value relationships (AOV £2.4M and £1.85M) |

### Inventory  Management

| Strategy | Action |
|----------|--------|
| **Reduce UK reliance** | Expand into Netherlands, EIRE, and Germany – online retail can operate globally |
| **Segment premium markets** | Segment Spain and France further by customer value, basket size, and repeat purchase behavior before launching premium or upsell campaigns |
| **Stock universal products** | Maintain inventory of cross-market products (OF4 Woodland, Carriage Jam Making Set, Spaceboy Lunch Box, Red Retrospot Cake Stand, Plasters in Tin, Red Toadstool LED Night Light) |

### For Marketing Strategy

| Strategy | Action |
|----------|--------|
| **Seasonal campaigns** | Target year-end promotions to capitalize on the "hockey stick" trend |
| **Product localization** | Prioritize UK best-sellers for Germany and EIRE markets (cultural similarity) |
| **Hero product focus** | Feature Regency Cakestand in EIRE, Rabbit Night Light in Germany, Round Snack Boxes in France |
| **Postage optimization** | Investigate EU fulfillment center to reduce shipping costs (currently 32-39% of international sales) |
---

## Summary

| Metric | Value |
|--------|-------|
| **Total Sales** | £9,747,747.93 |
| **Total Transactions** | 541,909 |
| **Average Order Value (AOV)** | £4,300 |
| **Top Market** | United Kingdom (84% of sales) |
| **Top Expansion Candidates** | Netherlands, EIRE, Germany, France |

