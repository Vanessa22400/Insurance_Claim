# Insurance Claim Risk Analytics: Cost Drivers, Risk Segmentation and Predictive Modeling  
*Understanding healthcare cost dynamics and identifying high-risk cases using data analytics and machine learning.*

**Dataset:** Health Insurance Dataset (1,338 individuals)  
**Techniques:** SQL analysis, exploratory data analysis (EDA), risk segmentation, K-Means clustering, causal inference (Propensity Score Matching), predictive modeling (Linear Regression & Random Forest), classification modeling, threshold tuning.  
**Key Insight:** Smoking is the strongest cost driver, increasing healthcare costs by approximately **4x** and playing a central role in high-cost claim risk.

---

## Project Context

This project focuses on how data analytics can support decision-making in an insurance context, particularly in understanding cost drivers and identifying higher-risk individuals.

It is part of a broader analytical exploration.  
A complementary project focuses on **preventive strategies and health outcomes**, extending these insights into a more prevention-oriented perspective.

---

## Business Context

In the insurance industry, understanding cost drivers and risk concentration is essential for pricing, portfolio management and long-term sustainability.

Key questions explored include:

- What factors drive higher healthcare costs?  
- How are costs distributed across the population?  
- Which individuals are more likely to generate high-cost claims?  
- How can models support better decision-making?  

---

## Dataset

Source:  
https://www.kaggle.com/datasets/mirichoi0218/insurance

- **1,338 individuals**
- **7 variables**
- no missing values
- fully anonymized

Main variables:

`age`, `sex`, `bmi`, `children`, `smoker`, `region`, `charges`

Healthcare costs range from ~$1,000 to over $63,000, highlighting a clear **high-cost segment**.

---

## Analytical Workflow

1. SQL-based exploration  
2. Exploratory Data Analysis (EDA)  
3. Risk segmentation  
4. Customer segmentation (clustering)  
5. Causal inference  
6. Predictive modeling (regression)  
7. Claim risk modeling (classification)  
8. Threshold tuning and decision analysis  

---

## Key Analyses

### SQL + Exploratory Analysis

Initial exploration shows strong differences across groups:

- smokers have ~4x higher costs than non-smokers  
- costs increase consistently with age  
- higher BMI is associated with higher costs  
- combined risk factors significantly amplify costs  

---

### Risk Segmentation

A simple risk score shows that:

- risk factors accumulate rather than act independently  
- higher risk scores lead to exponentially higher costs  
- a small high-risk group drives a large share of total expenses  

---

### Customer Segmentation (Clustering)

K-Means clustering identifies distinct population groups:

- young & low-cost segment  
- family segment  
- older population  
- high-risk lifestyle segment  

Each segment presents different cost patterns and risk levels.

---

### Causal Inference

Propensity Score Matching shows that:

- smoking increases costs by approximately **$23,500 per year**  
- even after controlling for other factors, the effect remains strong  

---

### Predictive Modeling

- Linear Regression (R² ≈ 0.78)  
- Random Forest (R² ≈ 0.86)  

Main drivers:

- smoking  
- BMI  
- age  

---

### Claim Risk Modeling (Classification)

A binary variable was created to identify individuals with higher likelihood of generating high-cost claims.

Models used:

- Logistic Regression  
- Random Forest Classifier  

Key results:

- Random Forest improves precision and overall performance  
- models can effectively distinguish high-risk individuals  

---

### Threshold Tuning and Decision Analysis

Instead of relying only on predictions, different probability thresholds were tested.

Key finding:

- lowering the threshold does **not improve recall**  
- but **increases false positives**  

👉 The default threshold (0.5) provides the best balance between risk detection and false alerts.

---

## Healthcare Cost Drivers Dashboard

![Healthcare Cost Dashboard](images/Healthcare_Cost_Dashboard.png)

**Figure:** Summary dashboard combining cost distribution, smoking impact, BMI effects, risk score behavior and feature importance.

---

## Key Insights

- **Smoking is the strongest cost driver**and a key factor associated with high-cost claims.
- Risk factors **accumulate and amplify costs**  
- A small group of individuals generates a disproportionate share of expenses  
- Predictive models can estimate costs and identify high-risk cases  
- Model decisions depend on how predictions are used, not only on accuracy  

---

## Business Applications

- improved cost forecasting  
- better understanding of risk concentration  
- identification of high-risk individuals  
- support for more structured decision-making  

---

## Limitations

- relatively small dataset  
- limited number of variables  
- no longitudinal data  

---

## Next Steps

- test additional machine learning models  
- incorporate more complex datasets  
- develop interactive dashboards  
- explore real-world insurance applications  

---

## Repository Structure

```
.
├── data
│ └── insurance.csv
├── notebooks
│ └── Insurance_Risk_Analytics.ipynb
├── images
│ └── Healthcare_Cost_Dashboard.png
├── requirements.txt
└── README.md
```

---

## Conclusion

This project shows how data analysis and predictive modeling can support better understanding of healthcare cost dynamics and risk patterns.

By combining multiple analytical approaches, it becomes possible to move from descriptive insights to more structured and actionable decision-making in an insurance context.


