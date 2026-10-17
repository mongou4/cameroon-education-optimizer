Secondary Education Resource Optimizer in Cameroon

Predicting GCE Advanced Level Performance via Structural Data Engineering

Executive Summary
This project mathematically models how structural resource constraints, specifically teacher pedagogy, classroom density, and funding impact academic outcomes in the Cameroonian secondary education system. By engineering composite metrics like the Pedagogical Impact Score (PIS), this analysis proves that strategic investments in teacher training yield higher returns on GCE Advanced Level pass rates than raw financial budget increases.

Rationale & Academic Context
As a mathematically trained educator currently studying mathematics and  computer science pedagogy, I built this model to bridge theoretical data science with actionable educational policy. European and Pan-African educational frameworks increasingly rely on data-driven resource allocation. This project simulates that exact pipeline, transforming raw, unstructured local inputs into prescriptive statistical insights.

Methodology: Synthetic Data Architecture
Due to the lack of granular, row-by-row open data from the Ministry of Secondary Education (MINESEC), I engineered a realistic synthetic dataset of 500 schools using numpy and pandas. The data distribution strictly mirrors the local reality of Cameroon:

Sector Weighting: 50% Government, 30% Lay Private, 20% Mission.

Geographic Distribution: 60% Urban / 40% Rural split, reflecting current urbanization indexes.

Constraint Modeling: Target variables (Pass Rates) are logically bound using NumPy clipping (np.clip(..., 15.0, 100.0)) to respect the physical limits of examination grading.

Feature Engineering (The Mathematical Engine)
Raw data alone does not capture classroom reality. I utilized Pandas apply() and lambda functions to build composite variables that reflect structural educational burdens:

1. STEM Student-Teacher Ratio
Calculates the numerical burden on specialized staff, preventing zero-division errors for severely deprived rural schools.


```python
Total_Students / (Math_Teachers + CS_Teachers)
```
2. Pedagogical Impact Score (PIS)
A custom metric proving that a highly trained teacher's effectiveness decays in an overcrowded classroom.

```python
(Pct_DIPES_Teachers * 10) / STEM_Student_Teacher_Ratio
```
Key Statistical Insights
(Note: See the visualizations/ folder for the Correlation Heatmap and Regression Scatter Plot)

The Pedagogy Premium (0.91 Correlation): The Pedagogical Impact Score has a near-perfect positive correlation with the GCE A-Level Pass Rate. This mathematically validates that trained teachers with manageable class sizes dictate academic success.

The Overcrowding Penalty (-0.47 Correlation): STEM Student-to-Teacher Ratios show a strong negative correlation with pass rates.

The Budget Ceiling (0.17 Correlation): Annual financial budget alone shows a surprisingly weak correlation to exam success, proving that throwing money at infrastructure without investing in human pedagogy is mathematically inefficient.

The Systemic Geographic Divide: Visual regression analysis reveals a dense clustering of Rural schools trapped in the low-impact (0-10 PIS) and low-pass-rate (40-60%) quadrant, while Urban Private and Mission schools dominate the upper quartiles.

Technical Stack
Language: Python 3.x

Data Engineering: pandas, numpy (Boolean masking, Lambda expressions, ETL pipelines)

Statistical Visualization: seaborn, matplotlib

Environment: Jupyter Notebook

How to Run This Project
Clone the repository: git clone [https://github.com/](https://github.com/)[your-username]/cameroon-edu-optimizer.git

