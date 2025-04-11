# 🧮 Customer Lifetime Value (CLV) Prediction | Python

## 📌 Objective
Predict the future value of customers based on historical purchase behaviour using both:
- Linear regression (interpretable baseline)
- Advanced probabilistic models (BG/NBD + Gamma-Gamma)

This project helps businesses **identify high-value customers**, optimise **retention strategy**, and forecast **customer-level revenue**.

---

## 🗃️ Dataset Overview

Simulated ecommerce dataset (`ecommerce_data.csv`) containing:
- CustomerID
- InvoiceNo
- InvoiceDate
- Quantity
- UnitPrice
- Country

A new column `TotalPrice = Quantity * UnitPrice` is derived for total purchase value.

---

## 🔧 Tools & Libraries
- Python (Pandas, NumPy)
- Seaborn & Matplotlib
- scikit-learn
- [lifetimes](https://github.com/CamDavidsonPilon/lifetimes) (for BG/NBD & Gamma-Gamma models)

---

## 📊 Methodology

### 1. 📦 Data Preprocessing
- Cleaned null/zero values
- Converted dates
- Calculated `TotalPrice`

### 2. 🧠 RFM Feature Engineering
- **Recency:** Days since last purchase
- **Frequency:** Number of invoices
- **Monetary:** Total spend

### 3. 🔍 CLV Modeling Approaches

#### A. Linear Regression
- Target: `Monetary`
- Features: `Recency`, `Frequency`
- Evaluated using R² and MSE

#### B. Probabilistic Model (BG/NBD + Gamma-Gamma)
- Predicted:
  - Number of future purchases (BG/NBD)
  - Average spend per purchase (Gamma-Gamma)
- Calculated 3-month CLV using:
```python
customer_lifetime_value(model, frequency, recency, T, monetary, time=3)
