# **Telecom-Churn-Risk-Analytics-using-Machine-Learning**
# **Team D | Evoastra Internship Project**

### 🧩 **Project Overview**

This project aims to predict market-level churn in the telecom industry — identifying operator × region (circle) combinations at risk of losing subscribers. By using machine learning, the project helps telecom providers proactively retain customers, allocate resources efficiently, and protect market share.

**Focus:** Market-level churn prediction (not individual customers)
**Final Model:** Random Forest Classifier
**Objective:** Detect early warning signs of subscriber loss and enable data-driven business decisions.

### 🚀 **Objectives**

  - Build an end-to-end churn prediction pipeline from raw telecom data.
  - Identify top churn drivers and generate interpretable business insights.
  - Deliver actionable recommendations for retention and marketing strategies.
  - Ensure the model is robust, explainable, and production-ready.

### 🧠 **Methodology**

#### **Phase 1 — Foundation & Market Intelligence**

  - Conducted data integrity checks and time range validation.
  - Performed exploratory analysis on subscriber trends, operator performance, and market dynamics.
  - Identified key business patterns and early hypotheses for churn causes.

#### **Phase 2 — Feature Engineering & Target Definition**

  - Created time-series features (rolling averages, volatility, and slopes).
  - Calculated market share, rank, and leader gap per circle.
  - Defined `future_churn` using month-over-month decline patterns.
  - Generated `phase2_features.csv` — the model-ready dataset.

#### **Phase 3 — Model Development & Validation**

  - Built and compared three models:
      - Logistic Regression (baseline)
      - Random Forest Classifier ✅ (final selection)
      - CatBoost (for benchmark comparison)
  - Evaluated using AUC, Precision, Recall, and F1-score.
  - Ensured temporal validation to avoid data leakage.

#### 📈 **Final Model (Random Forest) Performance**

| Metric    | Score |
| :-------- | :---- |
| AUC       | 0.960 |
| Precision | 0.628 |
| Recall    | 0.868 |
| F1-Score  | 0.729 |

✅ **Selected Model:** Random Forest Classifier (balanced performance + interpretability)

#### **Phase 4 — Business Analysis & Insight Generation**

  - Produced executive reports and playbooks explaining high-risk regions.
  - Identified top 10 high-risk operator–circle pairs using churn probabilities.
  - Linked model outputs to business recommendations:
      - **High-risk** → targeted retention campaigns
      - **Medium-risk** → engagement programs
      - **Low-risk** → maintain excellence

**Key Drivers Identified:**

  - **market\_share** — lower share indicates vulnerability.
  - **trend\_slope\_12** — negative trends show sustained loss.
  - **roll\_std\_6** — volatility signals unstable subscriber base.
  - **rank\_in\_circle** — lower rank means weaker competitive position.

📄 Reports generated in `/Reports/Phase-3` and `/Reports/Phase-4` include:

  - Model Comparison Report
  - Interpretability Summary
  - Risk Playbook
  - Executive Summary (PDF and Markdown)

#### **Phase 5 — Production Readiness (Next Step)**

Planned for final submission:

  - Automated scoring pipeline using trained Random Forest model.
  - Batch prediction generation (`phase4_predictions.csv`).
  - Dashboard integration for live risk monitoring.
  - Retraining policy to ensure model stability over time.

### 🧰 **Tech Stack**

| Category          | Tools / Libraries                                    |
| :---------------- | :--------------------------------------------------- |
| **Languages** | Python, SQL                                          |
| **Libraries** | pandas, NumPy, scikit-learn, matplotlib, seaborn, CatBoost |
| **Visualization** | Matplotlib, Seaborn                                  |
| **Model Persistence**| joblib                                             |
| **Report Generation**| ReportLab, Markdown                                |
| **Version Control**| Git & GitHub                                       |

### 💡 **Business Impact**

  - **Early Churn Detection:** Enables timely action before major loss.
  - **Optimized Resource Allocation:** Focused interventions in high-risk circles.
  - **Revenue Protection:** Retains key market segments proactively.
  - **Decision Intelligence:** Explains why churn happens, not just where.

### 🔍 **Insights at a Glance**

  - Circles with falling market share and rising volatility are high-risk.
  - Maintaining competitive rank is critical for long-term stability.
  - Early identification of churn-prone circles supports ROI-driven campaigns.

### 🌱 **Future Scope**

  - Integrate model outputs with a real-time analytics dashboard.
  - Include pricing and service quality data for richer modeling.
  - Automate retraining pipeline for ongoing monitoring.
  - Deploy through Flask/FastAPI for scoring and Power BI dashboards for visualization.

### 🏁 **Conclusion**

The Random Forest churn prediction model provides telecom operators with a data-backed framework for strategic retention and market intelligence. It bridges the gap between data science and business action, helping organizations make smarter, faster, and fairer decisions.

### 📁 **Project Structure**

```
📦 Telecom-Churn-Risk-Analytics
├── Data/
│   ├── metadata.csv
│   ├── year-month-circle-and-service-provider-wise-number-of-subscriptions-to-wireline-and-wireless-telecom-services-in-india.csv
│   ├── phase2_features.csv
│   └── phase4_predictions.csv
│
├── Models/
│   └── random_forest_model.pkl
│
├── Notebooks/
│   └── Major_Project_Team_D.ipynb
│
├── Reports/
│   ├── Phase-1/
│   │   ├── data_integrity_log.md
│   │   └── market_intelligence_memo.md
│   │
│   ├── Phase-2/
│   │   ├── churn_definition_memo.md
│   │   ├── feature_catalog.md
│   │   └── feature_validation_report.md
│   │
│   ├── Phase-3/
│   │   ├── model_comparison_report.md
│   │   ├── interpretability_summary.md
│   │   └── risk_playbook.md
│   │
│   └── Phase-4/
│       ├── executive_report_phase4.md
│       ├── pilot_roi_top3.csv
│       ├── prioritized_with_segments_playbooks.csv
│       ├── scored_operator_circle_full.csv
│       └── top100_prioritized.csv
│
└── README.md
```
