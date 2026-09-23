# Multiple Linear Regression – CO2 Emissions

This repository contains an end-to-end implementation of **multiple linear regression** to model **CO2 emissions** using real vehicle features.
The project focuses on **correct preprocessing, model interpretation, and visualization in real units**.

---

## Project Overview

We build and analyze linear regression models to predict **CO2 Emissions** based on:

- `ENGINESIZE`
- `FUELCONSUMPTION`

The notebook covers:
- Feature scaling and why it matters
- Training linear regression models with scikit-learn
- Recovering coefficients in original units after normalization
- Interpreting regression parameters
- Visualizing a **3D regression plane** with data points above and below the plane

---

## Files

- `Multiple_Linear_Regression.ipynb`: main notebook (run top to bottom)

---

## Dependencies

- `numpy`
- `pandas`
- `matplotlib`
- `scikit-learn`

---

## How Linear Regression Works (Brief Math)

### Model Form

For **multiple linear regression**, the model assumes a linear relationship between the target variable and the input features:

```
y = β₀ + β₁x₁ + β₂x₂ + ... + βₖxₖ
```

In this project:

```
CO2 = β₀ + β₁ · ENGINESIZE + β₂ · FUELCONSUMPTION
```

Where:
- `β₀` is the **intercept**
- `β₁, β₂` are the **feature coefficients**
- `x₁, x₂` are input features

---

### Learning Objective

The model learns parameters by minimizing the **Mean Squared Error (MSE)**:

```
MSE = (1 / n) · Σ (yᵢ − ŷᵢ)²
```

This is equivalent to solving the **normal equations**:

```
β = (XᵀX)⁻¹Xᵀy
```

---

### Effect of Standardization

When features are standardized:

```
x_std = (x − μ) / σ
```

The learned coefficients are in standardized space.
To interpret results in **real units**, coefficients are transformed back:

```
β_real = β_std / σ
β₀_real = β₀_std − Σ (μ · β_std / σ)
```

The notebook performs this conversion explicitly.

---

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/Helia-Karisani/Multiple_Linear_Regression.git
   cd Multiple_Linear_Regression
   ```

2. Open the notebook:
   ```bash
   jupyter notebook Multiple_Linear_Regression.ipynb
   ```

3. Run all cells from top to bottom.

---

## What the Notebook Covers

### 1. Data Preparation
- Load and inspect the dataset
- Select relevant numerical features
- Convert pandas objects to NumPy arrays

### 2. Feature Scaling
- Apply `StandardScaler`
- Why scaling is needed for learning and visualization
- Verify zero mean and unit variance

### 3. Train / Test Split
- Split data into training and testing sets
- Keep shapes consistent for scikit-learn

### 4. Model Training
- Train simple and multiple linear regression
- Extract coefficients and intercept

### 5. Model Interpretation
- Convert coefficients back to original feature units:
  ```
  CO2 = b0 + b1 · ENGINESIZE + b2 · FUELCONSUMPTION
  ```

### 6. Visualization
- 2D scatter plots
- 3D scatter with the regression plane
- Points colored by whether they lie above or below the plane
- Plotted in original units, not standardized space
