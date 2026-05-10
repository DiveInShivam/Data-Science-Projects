# 🛒 Customer Lifetime Value Prediction & Churn Risk Scoring
### UCI Online Retail Dataset | XGBoost · LightGBM · SHAP

---

## 📌 Overview

A dual-output ML pipeline predicting **90-day Customer Lifetime Value** and **Churn Probability**
built on the real UCI Online Retail dataset (541,909 transactions, 4,290 customers).

---

## 🏆 Model Results

| Model | Metric | Score |
|---|---|---|
| LightGBM Churn Classifier | **AUC-ROC** | **0.7499** |
| LightGBM Churn Classifier | **5-Fold CV AUC** | **0.7163 ± 0.02** |
| LightGBM Churn Classifier | **Accuracy** | **69%** |
| XGBoost CLV Regressor | **R²** (buyers only) | **0.0756** |
| XGBoost CLV Regressor | **MAE** | **£711** |

---

## 📂 Files

```
├── CLV_UCI_Real_Data.ipynb     ← Full analysis notebook (run this)
├── Online_Retail.xlsx          ← UCI dataset (download separately)
├── clv_dashboard_real.png      ← Results dashboard
├── README.md
```

---

## 🔧 How to Run

```bash
pip install pandas numpy xgboost lightgbm shap matplotlib seaborn openpyxl scikit-learn
jupyter notebook CLV_UCI_Real_Data.ipynb
```

---

## 🧠 Methodology

### Data Cleaning (Real UCI quirks handled)
- **135,080 rows** with missing CustomerID dropped (guest checkouts)
- **9,288 cancellation rows** removed (InvoiceNo starting with 'C')
- **Extreme outliers** capped at 99th percentile revenue (bulk wholesale orders: up to £168K/transaction)
- Zero and negative prices/quantities removed

### Temporal Split (No Data Leakage)
```
Dec 2010 ──────────────────── Sep 10, 2011 ──── Dec 09, 2011
[======= Observation (features) ========][== Label (90d) ==]
```

### Feature Engineering (14 features)
| Category | Features |
|---|---|
| RFM | recency, frequency, monetary |
| Behavioural | avg_order_val, avg_order_gap, unique_items, avg_qty, is_uk |
| Temporal | unique_months, freq_per_month |
| Advanced | spend_trend (monthly slope), recency_ratio (vs personal cadence) |
| Log-transformed | log_monetary, log_frequency |

### Models
- **XGBoost Regressor** — trained on buyers only to avoid zero-inflation
- **LightGBM Classifier** — scale_pos_weight handles 42.7% churn rate
- **Optimal threshold tuning** — sweeps 0.30–0.70 to maximise macro F1
- **5-Fold Cross-Validation** — proves stability (0.7163 ± 0.02)
- **SHAP TreeExplainer** — feature attribution for full transparency

---

## 💡 Key Findings

1. `log_monetary` is the #1 predictor — past spend predicts future spend
2. `recency_ratio` outperforms raw recency — customers overdue *relative to their own order cadence* are early churn signals
3. **306 High-Value customers** are at churn risk → £489,600 quarterly revenue at stake
4. High-Value segment (top 33%) generates **77% of total revenue**

---

## 📝 Resume Bullet Point

> **Customer Lifetime Value & Churn Prediction Engine** *(Python, XGBoost, LightGBM, SHAP)*  
> Built dual-output ML pipeline on 541K+ real UCI e-commerce transactions to predict 90-day CLV and churn risk. Achieved **AUC-ROC of 0.75** (5-fold CV: 0.72 ± 0.02) on churn classification with 69% balanced accuracy. Engineered 14 features including spend trend slope and recency-to-cadence ratio. Applied SHAP explainability to surface top drivers. Identified 306 high-value at-risk customers representing £490K quarterly revenue exposure.
