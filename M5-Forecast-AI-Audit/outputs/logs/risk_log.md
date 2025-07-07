# 🚨 Risk Log – M5 Forecast Audit

This file records identified risks across model development, explainability, and governance dimensions.

---

## ⚙️ Operational Risks

| Risk | Description | Mitigation |
|------|-------------|------------|
| Data Drift | Future sales patterns may shift due to seasonality or events | Retrain model quarterly |
| Feature Leakage | Lag features might overlap with label window | Time-series validation used |

---

## 📊 Model Risks

| Risk | Description | Mitigation |
|------|-------------|------------|
| Overfitting | XGBoost is prone to overfitting on small windows | Used early stopping, validation |
| Performance Degradation | RMSE may not capture impact on financial metrics | Audit SHAP-weighted business impact |

---

## 🧠 Explainability Risks

| Risk | Description | Mitigation |
|------|-------------|------------|
| Misinterpretation | SHAP and LIME may disagree on feature contribution | Triangulation with DiCE results |
| Counterfactual Plausibility | Some DiCE-generated scenarios may not be realistic | Mark unrealistic outputs with flags |

---

## ⚖️ Governance & Compliance

| Risk | Description | Mitigation |
|------|-------------|------------|
| ADM Transparency | Stakeholders may not understand model logic | Include SHAP and LIME visualizations |
| Documentation Gaps | Trace may be lost if model is retrained | Log all modeling steps in `audit_trace_log.md` |
