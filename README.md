## Overview
This project provides a comprehensive exploratory data analysis (EDA) on a large-scale health indicators dataset containing **253,680 rows** and **22 columns**. The primary objective is to investigate the relationships between various lifestyle factors, health conditions, demographics, and the prevalence of **Heart Disease or Attacks** (the target variable). 

By conducting statistical analysis, univariate profiling, bivariate correlation checks, and demographic stratifications, this project surfaces actionable insights regarding major risk factors such as High Blood Pressure, High Cholesterol, BMI, Age, and Education level.

---

## Repository Structure
Based on the project configuration shown in `image_9256f4.png`, the directory is organized as follows:

```text
├── Datasets/
│   ├── Health and demographic data d...
│   └── heart_disease_health_indicators...
├── Notebook/
│   └── Project_Notebook.ipynb
├── Report/
│   └── Final Research Report on Health...
└── README.md
```

*   **Datasets/**: Contains the raw and reference data files used for analysis.
*   **Notebook/**: Houses the core Jupyter notebook (`Project_Notebook.ipynb`) containing all Python code, step-by-step documentation, and inline visualizations.
*   **Report/**: Holds the comprehensive research findings summary document.

---

## Dependencies & Tools
The analysis is implemented in Python utilizing the following standard data science libraries:
*   **Pandas (`pd`)**: For robust dataset loading, manipulation, aggregation, and cross-tabulations.
*   **NumPy (`np`)**: Supporting scientific and vectorized numerical operations.
*   **Matplotlib (`plt`)**: For foundational plotting and detailed chart customizations.
*   **Seaborn (`sns`)**: For high-level, aesthetically polished statistical visualizations.

---

## Step-by-Step Methodology & Key Insights

### 1. Initial Data Profiling & Statistical Assessment
Before deep-diving into visualizations, the dataset was rigorously profiled using pandas functions:
*   `df.head()`: Provided a quick view of column names, data structures, and binary/numerical/categorical attributes.
*   `df.info()`: Confirmed a total of 253,680 observations, 22 distinct variables, and verified that no data columns suffered from structural data type mismatches or missing values.
*   `df.describe()`: Yielded a descriptive statistical summary detailing the mean, median, standard deviation, and min/max ranges for each health feature.
*   `df.isnull().sum()`: Assured absolute data completeness by verifying zero missing values across all entries.

---

### 2. Uni-Variate Analysis (Distribution Analysis)
Individual health traits and demographics were mapped out to understand their skewness and baseline representation:
*   **Age Distribution (Histogram)**: Shorter bars on the younger age groups and a significant increase toward the right end (Age groups 10, 12, 13) reveal that the dataset is heavily skewed toward older individuals.
*   **Body Mass Index (Bar Chart)**: The distribution of BMI is positively skewed with a long tail stretching to the right. While most individuals fall into standard ranges, a subset exhibits very high BMI readings.
*   **Mental & Physical Health (Histograms)**: 
    *   `MentHlth`: 175,680 individuals reported 0 days of poor mental health out of the past 30 days.
    *   `PhysHlth`: 160,052 individuals reported 0 days of poor physical health out of the past 30 days.
    *   *Insight*: The vast majority of the surveyed population maintains stable and good perceived baseline health.
*   **Prevalence of Risk Factors & Demographics**:
    *   `HighBP`: 144,851 (57.10%) individuals have No High Blood Pressure, while 108,829 (42.90%) have High Blood Pressure.
    *   `HighChol`: 146,089 (57.59%) have No High Cholesterol, while 107,591 (42.41%) have High Cholesterol.
    *   `Smoker`: 141,257 non-smokers compared to 112,423 individuals who have smoked at least 5 packs of cigarettes.
    *   `Gender`: Balanced representation with 141,974 females and 111,706 males.
*   **Target Variable - Heart Disease / Attack**:
    *   **90.58%** of the population reported **No Heart Disease or Attack**, while **9.42%** tested positive for the condition.

---

### 3. Bi-Variate Analysis (Correlations & Inter-relationships)
Cross-tabulations and comparative charts were built to discover hidden dependencies:
*   **High Blood Pressure vs. Heart Disease**: 
    *   Of those with High BP, **75.05%** have experienced Heart Disease, compared to only **24.69%** of those with normal BP. This strongly indicates that high blood pressure severely increases heart attack probabilities.
*   **High Cholesterol vs. Heart Disease**:
    *   **70.11%** of individuals with High Cholesterol exhibit Heart Disease, whereas only **29.88%** of non-high-cholesterol individuals face the condition.
*   **BMI and Heart Disease (Boxplot)**:
    *   The median BMI for the "No Heart Disease" group is ~27, while the "Heart Disease" cohort shows a higher median of ~29. The upper quartile bounds are also visibly shifted higher for the heart disease cohort.
*   **Correlation Matrix Heatmaps**:
    *   `Income` & `BMI` share a weak negative correlation (**-0.10**), implying higher-income brackets exhibit a marginal tendency toward a lower BMI.
    *   `Smoking` & `Mental Health` possess a weak positive correlation (**0.09**).
    *   `Smoking` & `Heart Disease` possess a weak positive correlation (**0.11**).
*   **Age vs. BMI (Scatter Plot)**: 
    *   No clear upward or downward linear trend was visible across age cohorts, showing an absence of linear correlation between BMI and aging categories.

---

### 4. Demographic Stratifications (Pivot Table Insights)
Using `df.pivot_table(aggfunc='mean') * 100`, the prevalence rates of heart disease across social metrics were uncovered:
*   **Age-Group Prevalence**: There is a clear, aggressive upward trend. As the age bracket indices rise, the percentage of heart disease cases escalates dramatically, reinforcing age as a primary independent risk factor.
*   **Education-Level Prevalence**: A clear negative correlation was detected. As an individual's level of education advances, the risk and prevalence rate of a heart attack steadily declines. This signals strong socioeconomic disparities regarding preventive health awareness.

---

## How to Get Started
1. Clone or download this repository onto your machine.
2. Ensure you have python installed along with required packages: `pip install pandas numpy matplotlib seaborn jupyter`
3. Launch your terminal and start the server: `jupyter notebook`
4. Navigate to `Notebook/Project_Notebook.ipynb` and execute the cells sequentially to reproduce the visual findings and statistical metrics.
