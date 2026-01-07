**Firm-Level Credit Risk Early-Warning System**

**Overview**

This project develops a forward-looking firm-level credit risk early-warning system to predict one-year-ahead default risk using company financial fundamentals and macroeconomic indicators. The goal is to compare human heuristic credit assessment, classical statistical models, and machine-learning approaches under a consistent and realistic validation framework.

The project emphasizes economic interpretability, time-consistent modeling, and business usability rather than purely optimizing predictive accuracy.

**Key Questions**

How effective are rule-based credit scores compared to data-driven models?

How much incremental value does machine learning add beyond classical statistics?

Can model outputs be translated into actionable credit risk insights?

**Data**

Firm Financials: S&P Capital IQ (annual fundamentals)

Macroeconomic Variables: GDP growth, unemployment rate, financial conditions (FRED)

Default Proxy: Forward-looking financial distress indicator (t+1)

The dataset is structured as a firm-year panel and uses only information available at the time of prediction to avoid look-ahead bias.

**Methodology**

Three modeling approaches are implemented and compared:

Altman-Style Rule-Based Score
Human-interpretable heuristic benchmark using fixed financial ratio weights.

Logistic Regression
Classical statistical credit model estimating linear relationships between predictors and default risk.

Random Forest
Machine-learning model capturing nonlinear effects, interactions, and missing-data patterns.

All models are evaluated using time-based train/test splits.

**Results**

Out-of-sample performance is evaluated using AUC and KS statistics:

Model	AUC	KS
Altman-Style Rules	~0.55	~0.14
Logistic Regression	~0.64	~0.28
Random Forest	~0.71	~0.38

Results show that most predictive gains come from moving from heuristic rules to statistical models, while machine learning provides incremental improvements.

**Risk Buckets and Business Use**

Predicted probabilities of default from the Random Forest model are grouped into decile-based risk buckets. Observed default rates increase monotonically from the lowest-risk bucket (0) to the highest-risk bucket (9), demonstrating stable and intuitive risk rankings.

Firm-level outputs are exported for each bucket, enabling:

Monitoring watchlists

Credit review prioritization

Portfolio risk concentration analysis

**Key Takeaways**

Rule-based credit scores provide limited discrimination

Logistic regression captures most available signal

Machine learning improves performance incrementally, not magically

Missing financial data itself is a strong risk signal

Economic intuition and validation matter more than model complexity

**Limitations and Future Work**

Default is proxied using a distress indicator rather than legal bankruptcy

Annual data limits short-term forecasting granularity

Future extensions include macro–financial forecasting, stress testing, and calibration analysis

**Author**

Ozoemena Augustine
January 7th 2026
