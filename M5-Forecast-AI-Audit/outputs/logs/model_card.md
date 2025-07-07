# 🧾 Model Card – M5 Forecast Audit (XGBoost)

**Model Type:** Gradient Boosting Regressor (XGBoost)  
**Dataset:** M5 Forecasting Accuracy (Kaggle)  
**Use Case:** Retail sales forecast for California, FOODS category

---

## 🎯 Model Purpose

This model is designed to predict short-term product-level sales for inventory optimization and demand planning. It serves as a test case for explainability-driven auditing using SHAP, LIME, and DiCE.

---

## ⚙️ Model Configuration

- **Features used:** day of week, promo, price, snap, lag sales, rolling mean
- **Target variable:** daily unit sales
- **Training range:** Last 4.5 years of available data
- **Validation:** Time-series split (non-randomized)

---

## 📈 Performance

| Metric | Value |
|--------|-------|
| RMSE   | 2.19  |
| MAE    | 1.72  |
| R²     | 0.84  |

Performance metrics are point-in-time and may change across retrains.

---

## 🔍 Explainability Tools Applied

- **SHAP:** Feature importance (global & local)
- **LIME:** Instance-level prediction rationale
- **DiCE:** Counterfactuals to evaluate edge case behavior

---

## 🧩 Governance and Risk

- Aligns with NIST AI RMF mapping
- Includes audit trace from data ingest to ADM output
- Risk log maintained separately in `risk_log.md`

---

## ⚠️ Limitations

- Model was built for simulation, not production
- Counterfactuals are illustrative, not operational
- Performance is optimized for traceability, not accuracy
