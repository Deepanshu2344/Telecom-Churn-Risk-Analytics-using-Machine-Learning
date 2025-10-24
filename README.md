# Telecom-Churn-Risk-Analytics-using-Machine-Learning

🧩 Project Overview

This project aims to predict market-level churn in the telecom industry — identifying operator × region (circle) combinations at risk of losing subscribers.
By using machine learning, the project helps telecom providers proactively retain customers, allocate resources efficiently, and protect market share.

Focus: Market-level churn prediction (not individual customers)
Final Model: Random Forest Classifier
Objective: Detect early warning signs of subscriber loss and enable data-driven business decisions.

🚀 Objectives

- Build an end-to-end churn prediction pipeline from raw telecom data.
- Identify top churn drivers and generate interpretable business insights.
- Deliver actionable recommendations for retention and marketing strategies.
- Ensure the model is robust, explainable, and production-ready.

🧠 Methodology
Phase 1 — Foundation & Market Intelligence

- Conducted data integrity checks and time range validation.
- Performed exploratory analysis on subscriber trends, operator performance, and market dynamics.
- Identified key business patterns and early hypotheses for churn causes.

Phase 2 — Feature Engineering & Target Definition

- Created time-series features (rolling averages, volatility, and slopes).
- Calculated market share, rank, and leader gap per circle.
- Defined future_churn using month-over-month decline patterns.
- Generated phase2_features.csv — the model-ready dataset.

Phase 3 — Model Development & Validation

- Built and compared three models:
Logistic Regression (baseline)
Random Forest Classifier ✅ (final selection)
CatBoost (for benchmark comparison)
- Evaluated using AUC, Precision, Recall, and F1-score.
- Ensured temporal validation to avoid data leakage.

📈 Final Model (Random Forest) Performance:

Metric	Score
AUC	0.960
Precision	0.628
Recall	0.868
F1-Score	0.729

✅ Selected Model: Random Forest Classifier (balanced performance + interpretability)

Phase 4 — Business Analysis & Insight Generation

- Produced executive reports and playbooks explaining high-risk regions.
- Identified top 10 high-risk operator–circle pairs using churn probabilities.
- Linked model outputs to business recommendations:
High-risk → targeted retention campaigns
Medium-risk → engagement programs
Low-risk → maintain excellence

Key Drivers Identified:
market_share — lower share indicates vulnerability.
trend_slope_12 — negative trends show sustained loss.
roll_std_6 — volatility signals unstable subscriber base.
rank_in_circle — lower rank means weaker competitive position.

📄 Reports generated in /Reports/Phase-3 and /Reports/Phase-4 include:
Model Comparison Report
Interpretability Summary
Risk Playbook
Executive Summary (PDF and Markdown)

Phase 5 — Production Readiness (Next Step)

Planned for final submission:
- Automated scoring pipeline using trained Random Forest model.
- Batch prediction generation (phase4_predictions.csv).
- Dashboard integration for live risk monitoring.
- Retraining policy to ensure model stability over time.

🧰 Tech Stack
Category	Tools / Libraries
Languages	Python, SQL
Libraries	pandas, NumPy, scikit-learn, matplotlib, seaborn, CatBoost
Visualization	Matplotlib, Seaborn
Model Persistence	joblib
Report Generation	ReportLab, Markdown
Version Control	Git & GitHub
