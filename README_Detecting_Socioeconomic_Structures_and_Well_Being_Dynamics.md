# Detecting Socioeconomic Structures and Well-Being Dynamics  
### An Exploratory Data Analysis within the Digital Humanities Framework  

## Overview  

This repository presents an **Exploratory Data Analysis (EDA)** and multivariate modelling study of a structured socioeconomic and lifestyle dataset comprising **30 individual-level observations and 10 numerical variables**.  

The project is situated within a **Digital Humanities (DH)** framework and integrates descriptive statistics, regression modelling, dimensionality reduction, and unsupervised learning in order to uncover latent socioeconomic and well-being structures.

This study constitutes the **Second Assignment for the Data Analytics course** of the **MSc Digital Humanities programme**, jointly offered by the National and Kapodistrian University of Athens, the University of Cyprus, and the ATHENA Research Centre.

---

## Research Objectives  

The project addresses the following research questions:

- What are the distributional and dispersion properties of key socioeconomic and lifestyle variables?
- Do statistically significant outliers exist, and how should they be treated?
- What linear relationships structure the dataset?
- Can income, age, and labour intensity explain variation in expenditure, health, savings, and satisfaction?
- What latent structural dimensions emerge through Principal Component Analysis (PCA)?
- Can natural socioeconomic groupings be detected using K-means clustering?

---

## Dataset Description  

The dataset consists of **30 observations** and includes **10 numerical variables** capturing demographic, economic, behavioural, and well-being dimensions.  

Each observation corresponds to an individual and is described by the following variables:

### Dataset Variables  

| Variable Name | Data Type | Description |
|---------------|-----------|-------------|
| id | Numerical (Identifier) | Unique identifier (excluded from modelling) |
| age | Numerical | Age of the individual (years) |
| income | Numerical | Annual income (monetary units) |
| education_years | Numerical | Total years of formal education |
| weekly_work_hours | Numerical | Average weekly working hours |
| health_index | Numerical | Composite physical health indicator (0–1 scale) |
| satisfaction_score | Numerical | Subjective life satisfaction (1–10 scale) |
| monthly_expenditure | Numerical | Average monthly consumption expenditure |
| savings | Numerical | Accumulated financial savings |
| commute_time_minutes | Numerical | Average daily commute time (minutes) |

The balanced inclusion of demographic, financial, behavioural, and evaluative indicators enables a **multidimensional analytical perspective** that captures both material conditions and subjective well-being.

---

## Data Quality  

- No missing values were detected across any variables  
- No duplicate observations were identified  
- All variables are continuous (integer or float), ensuring compatibility with parametric statistical methods  
- Statistical outliers were detected in `education_years` and treated using **IQR-based winsorisation (capping)** rather than deletion, in order to preserve sample size and interpretability  

Following preprocessing, the dataset exhibits improved dispersion stability while maintaining full observational completeness.

---

## Methodology  

### Exploratory Data Analysis (EDA)  

- Descriptive statistics (mean, median, variance, IQR)
- Distributional analysis using:
  - Histograms
  - Box plots
- Outlier detection using the **Interquartile Range (IQR)** method
- Pearson correlation matrix and heatmap
- Scatter plots for bivariate inspection

EDA serves as the foundational analytical layer guiding subsequent modelling decisions.

---

### Statistical Modelling  

#### Simple Linear Regression  

Three exploratory simple regression models were estimated:

- **Income → Monthly Expenditure**
- **Age → Health Index**
- **Weekly Work Hours → Savings**

These models quantify the strength and direction of key socioeconomic relationships using regression coefficients and \( R^2 \) values.

#### Multiple Linear Regression  

Three multivariate configurations were examined:

- **Satisfaction Score** predicted by income, savings, expenditure, work hours, commute time, education, and health  
- **Income** predicted by savings, expenditure, and work hours  
- **Age** predicted by health index and satisfaction score  

The modelling strategy emphasises **interpretative insight** and structural understanding rather than predictive optimisation.

---

### Dimensionality Reduction  

#### Principal Component Analysis (PCA)  

- Standardisation of numerical variables (excluding `id`)
- Extraction of **three principal components**
- Preservation of **over 90% of total variance**
- 2D and 3D PCA visualisations to detect latent structural gradients

PCA reveals a dominant **socioeconomic gradient** supplemented by secondary behavioural and well-being dimensions.

---

### Unsupervised Learning  

#### K-Means Clustering  

- Applied to standardised data  
- Number of clusters: **k = 4**  
- Cluster interpretation conducted within PCA space  

Clustering analysis identifies income-based stratification patterns and highlights internal heterogeneity within the middle-income group.

---

## Key Findings  

- The dataset is organised around a **dominant socioeconomic gradient** structured primarily by income, expenditure, savings, and work intensity  
- A distinct **well-being axis** emerges, strongly structured around age and health status  
- Income strongly predicts expenditure  
- Age robustly predicts health decline  
- Work intensity moderately predicts savings  
- Health is the strongest determinant of life satisfaction when controlling for economic variables  
- PCA confirms the structural coherence of the economic cluster  
- K-means clustering reveals cohesive low- and high-income clusters and heterogeneity within the middle-income group  

Overall, the study demonstrates that integrated statistical and unsupervised learning techniques can illuminate meaningful structural patterns even within relatively small datasets.

---

## Repository Structure  

├── CODE_Detecting_Socioeconomic_Structures_and_Well_Being_Dynamics.ipynb  

├── README.md  

├── REPORT_Detecting_Socioeconomic_Structures_and_Well_Being_Dynamics.pdf  

---

## License  

**Academic Use – Coursework License**  

This repository contains the Second Assignment for the **Data Analytics course** of the **MSc Digital Humanities programme**.  

The material is intended **exclusively for academic, educational, and research purposes**.  
Reuse, modification, or redistribution for commercial purposes is not permitted without explicit permission from the author.

---

## Author  

**Constantinos Panayi**  
MSc Digital Humanities  
National and Kapodistrian University of Athens · University of Cyprus · ATHENA Research Centre
