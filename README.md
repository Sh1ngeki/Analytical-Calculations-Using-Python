# Analytical-Calculations-Using-Python

# Statistical Hypothesis Testing Analysis

Analysis code for testing proportions and outlier detection in salary data.

## Setup

Required packages:
```python
numpy
scipy
pandas
matplotlib
```

## Project Structure

The project contains two main analyses:

### 1. Proportion Hypothesis Testing

Tests whether more than 60% of users use the premium package.

Sample parameters:
- Sample size (n): 200
- Successes (x): 105
- Test proportion (pr_0): 0.6

Key calculations:
- Standard error
- Z-statistic
- P-value
- Decision making with α = 0.05

### 2. Outlier Detection

Analyzes salary data using two methods:
- Z-score method (|z| > 3)
- IQR method (1.5 × IQR)

Includes visualizations:
- Box plots by department
- Outlier statistics

## Usage

1. Load the data:
```python
df = pd.read_csv('earnings.csv')
```

2. Run hypothesis test:
```python
# Calculate sample proportion
pr_hat = x/n

# Calculate standard error
std_error = np.sqrt(pr_0 * (1 - pr_0) / n)

# Calculate z-statistic
z_stat = (pr_hat - pr_0) / std_error
```

3. Detect outliers:
```python
# Z-score method
df['z_score'] = (df['Salary'] - df['Salary'].mean()) / df['Salary'].std()
df_no_outliers = df[np.abs(df['z_score']) <= 3]

# IQR method
Q1 = df['Salary'].quantile(0.25)
Q3 = df['Salary'].quantile(0.75)
IQR = Q3 - Q1
```

## Output

The code generates:
- Hypothesis test results
- Box plots of salary distribution
- Outlier analysis reports
