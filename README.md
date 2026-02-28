# Multiple Linear Regression – CO2 Emissions

This repository contains a complete, end-to-end implementation of **multiple linear regression** to model **CO2 emissions** using real vehicle features.  
The project emphasizes **correct preprocessing, model interpretation, and visualization in real units**.

---

## 📌 Project Overview

We build and analyze linear regression models to predict **CO2 Emissions** based on:

- `ENGINESIZE`
- `FUELCONSUMPTION`

The notebook demonstrates:
- Feature scaling and why it matters
- Training linear regression models with scikit-learn
- Recovering coefficients in original units after normalization
- Interpreting regression parameters
- Visualizing a **3D regression plane** with data points above and below the plane (THIS MIGHT BE MISSING)

---

## 📂 Files

- `Multiple_Linear_Regression.ipynb` — Main notebook (run top to bottom)

---

## ⚙️ Dependencies

This project uses standard Python data-science libraries:

- `numpy`
- `pandas`
- `matplotlib`
- `scikit-learn`

---

## 🧮 How Linear Regression Works (Brief Math)

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

(scikit-learn computes this efficiently using numerical linear algebra)

---

### Effect of Standardization

When features are standardized:

```
x_std = (x − μ) / σ
```

The learned coefficients correspond to standardized space.  
To interpret results in **real units**, coefficients must be transformed back:

```
β_real = β_std / σ
β₀_real = β₀_std − Σ (μ · β_std / σ)
```

This notebook explicitly performs this conversion.

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone <your-repo-url>
   cd <repo-name>
   ```

2. Open the notebook:
   ```bash
   jupyter notebook Multiple_Linear_Regression.ipynb
   ```

3. Run **all cells from top to bottom**

---

## 🧠 What the Notebook Covers

### 1. Data Preparation
- Load and inspect the dataset
- Select relevant numerical features
- Convert pandas objects to NumPy arrays

### 2. Feature Scaling
- Apply `StandardScaler`
- Explain why scaling is needed for learning and visualization
- Verify zero mean and unit variance

### 3. Train / Test Split
- Split data into training and testing sets
- Ensure consistent shapes for scikit-learn

### 4. Model Training
- Train:
  - Simple linear regression
  - Multiple linear regression
- Extract coefficients and intercept

### 5. Model Interpretation
- Convert coefficients **back to original feature units**
- Understand the regression equation in real-world terms:
  ```
  CO2 = b0 + b1 · ENGINESIZE + b2 · FUELCONSUMPTION
  ```

### 6. Visualization
- 2D scatter plots
- **3D scatter + regression plane**
- Points colored by whether they lie **above or below** the regression plane
- Visualization performed **in original units**, not standardized space

---

## ✅ Final Outcome

By the end of the notebook, we:

- Train accurate linear regression models
- Understand how scaling affects learning and visualization
- Correctly interpret model parameters
- Recover coefficients in real units
- Produce a clean 3D visualization of a regression plane

---

## 📄 License

This project is provided for educational purposes.
