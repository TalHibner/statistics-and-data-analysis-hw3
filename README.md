# Statistics and Data Analysis - Homework 3

## Assignment Overview
This assignment focuses on statistical analysis and correlation analysis with two major components:
1. **Correlation Analysis**: Understanding different correlation measures and their relationships
2. **Medical Data Analysis**: Comprehensive statistical analysis of the UCI Heart Disease dataset

---

## Part 1: Correlation Analysis (14 points)

### Objectives
Understand the nuances between different correlation coefficients:
- **Pearson correlation (r)**: Linear relationship between variables
- **Spearman correlation (ρ)**: Rank-based monotonic relationship
- **Kendall correlation (τ)**: Rank-based concordance

### Key Concepts
- How outliers affect different correlation measures
- Theoretical bounds and constraints between correlation types
- The Daniels inequality: $|3\tau - 2\rho| \leq 1$
- Visualization of correlation relationships using jointplots and marginal distributions

### Challenges Addressed
1. **1.A**: Creating data with strong negative Pearson correlation but strong positive when outlier removed
2. **1.B**: Proving impossibility of perfect Spearman correlation that drops below 0.9 when removing one point
3. **1.C**: Finding data where Kendall τ > Spearman ρ + 0.45
4. **1.D**: Finding data where Kendall τ < Spearman ρ - 0.45
5. **1.E**: Creating data where Pearson < Spearman - 0.6 (effects of outliers on linear vs. rank correlations)
6. **1.F**: Demonstrating Pearson > Spearman + 1.2
7. **1.G**: Proving impossibility using mathematical bounds

---

## Part 2: UCI Heart Disease Dataset Analysis (38 points)

### Dataset Details
- **Source**: UCI Machine Learning Repository (Detrano et al., 1989)
- **Records**: 303 patient observations
- **Features**: 13 medical measurements
- **Target**: Presence/absence of heart disease

### Numerical Features
- `age`: Age in years
- `trestbps`: Resting blood pressure (mm Hg)
- `chol`: Serum cholesterol (mg/dl)
- `thalach`: Maximum heart rate achieved
- `oldpeak`: ST depression induced by exercise

### Categorical Features
- `sex`: Gender (0=F, 1=M)
- `cp`: Chest pain type
- `fbs`: Fasting blood sugar > 120 mg/dl
- `restecg`: Resting electrocardiographic results
- `exang`: Exercise-induced angina
- `slope`: Slope of ST segment
- `ca`: Number of major vessels (0-3)
- `thal`: Thalassemia type

### Key Analysis Tasks

#### 1. **Data Preprocessing**
- Identify and impute missing values
- Numerical features: use median
- Categorical features: use mode
- Binary classification of target (0 = healthy, 1 = disease)

#### 2. **Confidence Intervals (95%)**
Determine which numerical features show statistically significant mean differences between healthy and disease populations using confidence intervals.

#### 3. **Distribution Analysis**
- Fit probability distributions to each numerical feature using MLE
- Compare observed distributions with fitted models
- Test for normality and other distribution types (exponential, gamma, lognormal)

#### 4. **Correlation Analysis**
- Calculate pairwise Pearson correlations for all numerical features
- Assess statistical significance of correlations
- Create jointplots with marginal histograms for significant pairs
- Fit bivariate normal distributions and visualize 2D PDFs

#### 5. **Demographic & Health Status Splits**
Analyze whether correlation patterns differ by:
- **Gender**: Male vs. Female correlations
- **Health Status**: Disease vs. Healthy populations
- Create comparative visualization matrices

#### 6. **Age-Based Feature Patterns**
- Partition data into age bins
- Create violin plots for each numerical feature (except age) split by health status
- Visualize how features vary across age groups

#### 7. **Original Research Question**
Identify and address at least one novel research question from the data (e.g., interaction effects, non-linear patterns, subgroup differences).

---

## Key Challenges

### Statistical Challenges
1. **Missing Value Imputation**: Choosing appropriate imputation methods without introducing bias
2. **Distribution Fitting**: Selecting correct theoretical distributions and computing MLE parameters
3. **Multiple Testing**: Controlling for false positives with many correlation tests
4. **Robust Statistics**: Understanding how outliers affect different correlation measures

### Computational Challenges
1. **Visualization**: Creating complex multi-panel plots with marginal distributions
2. **Bivariate Analysis**: Estimating and plotting 2D normal distributions
3. **Statistical Testing**: Computing p-values and confidence intervals correctly

### Conceptual Challenges
1. **Correlation vs Causation**: Interpreting significant correlations in medical data
2. **Subgroup Differences**: Understanding how demographics affect relationships
3. **Feature Interactions**: Identifying potential non-linear or interactive patterns
4. **Domain Knowledge**: Understanding medical context of features

---

## Tools & Libraries
- **NumPy**: Numerical computation and array operations
- **Pandas**: Data manipulation and exploration
- **SciPy**: Statistical functions (distributions, hypothesis testing, correlations)
- **Matplotlib & Seaborn**: Data visualization
- **Warnings**: Suppress non-critical warnings during analysis

---

## Results & Output
- Detailed statistical summaries with p-values
- Visualizations: histograms, jointplots, violin plots, heatmaps
- Correlation matrices and significance tests
- Bivariate normal distribution fits and contour plots
- Report with clear conclusions and clinical insights

---

## Submission Requirements
- **Format**: Single Jupyter Notebook (HW3.ipynb)
- **Naming**: `{ID1}_{ID2}.ipynb` (pair) or `{ID}.ipynb` (individual)
- **Content**: All questions answered with code, visualizations, and markdown explanations
- **Mathematical notation**: Use LaTeX in markdown cells

---

## References
1. Detrano, R., Janosi, A., Steinbrunn, W., et al. (1989). International application of a new probability algorithm for the diagnosis of coronary artery disease. *American Journal of Cardiology*, 64, 304-310.
2. UCI Machine Learning Repository: https://archive.ics.uci.edu/ml/datasets/heart+disease
3. Kaggle Heart Disease Dataset: https://www.kaggle.com/ronitf/heart-disease-uci
