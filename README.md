# End-to-End Data Pipeline & Fraud Risk Analytics: FinTrust National Bank

An automated, cross-functional data pipeline and advanced fraud analytics initiative that processes over 150,000 synthetic banking records across ten distinct datasets. It features an interactive Power BI dashboard to expose critical security vulnerabilities and implements the foundational logic for a rule-based statistical risk score to proactively mitigate financial leakage.

## 1. Project Overview
This project builds a robust data engineering and fraud analytics solution for FinTrust National Bank. By extracting raw, messy synthetic data from a relational database, executing an objective data cleaning pipeline in Python, and performing advanced Exploratory Data Analysis (EDA), the project uncovers an 8.1% baseline fraud rate. The clean data feeds directly into a multi-page Power BI dashboard, translating transactional anomalies into actionable operational defense strategies for risk management teams.

## 2. Purpose
In retail banking, static security rules and single-threshold blocking create high rates of false positives, disrupting legitimate customers while failing to catch sophisticated fraud vectors. The purpose of this project is to model real-world banking anomalies and establish a holistic prevention ecosystem. By breaking down disconnected transaction, customer, and log tables into an integrated data system, the bank can transition from a slow, reactive operational loop to proactive, data-driven security controls.

## 3. Tech Stack
The technical architecture utilized to develop and execute this end-to-end pipeline includes:
*   **Database & Engineering:** MySQL / SQL Server, Stored Procedures (used to simulate core database architectures and schema generation).
*   **Pipeline Connection:** SQLAlchemy & `pymysql` (programmatic database connector to stream data directly into Python DataFrames).
*   **Data Processing & Analytics:** Python, Jupyter Notebooks (`pandas` for heavy structural cleaning and datetime synchronization, `numpy` for high-performance mathematical modeling).
*   **Business Intelligence:** Power BI (connected directly to processed datasets to deploy automated, interactive risk reports).

## 4. Data Architecture
The relational database pipeline models ten complex, interconnected schema tables containing over 150,000 records:
*   **Customers:** customer_id, customer_name, gender, age, city, state, occupation, annual_income, kyc_status, customer_since, risk_category.
*   **Branches:** branch_id, branch_name, city, state, region, branch_manager, opening_date, branch_type.
*   **Merchants:** merchant_id, merchant_name, merchant_category, merchant_city, risk_level, chargeback_rate.
*   **Accounts:** account_id, customer_id, branch_id, account_type, account_open_date, account_status, current_balance, avg_monthly_balance.
*   **Credit Cards:** card_id, customer_id, card_type, credit_limit, available_limit, issue_date, expiry_date, card_status.
*   **Device Logins:** login_id, customer_id, device_id, ip_address, login_city, login_datetime, login_status, device_type.
*   **Transactions:** transaction_id, customer_id, account_id, card_id, transaction_datetime, transaction_amount, transaction_type, channel, merchant_id, transaction_city, transaction_status, is_fraud, fraud_type.
*   **ATM Logs:** atm_log_id, customer_id, account_id, atm_id, atm_city, withdrawal_amount, attempt_status, attempt_datetime, failed_attempt_count.
*   **Fraud Alerts:** alert_id, transaction_id, alert_type, risk_score, alert_status, investigation_result, created_datetime, resolved_datetime.
*   **Chargebacks:** chargeback_id, transaction_id, customer_id, reason_code, chargeback_amount, reported_date, status.

## 5. Features

### Business Problem
Modern financial fraud is decentralized and highly adaptive. Relying on disconnected tables or manual tracking creates visibility gaps, allowing fraudsters to exploit cross-channel vulnerabilities (e.g., matching late-night card use with brute-force ATM failures). Furthermore, manual file prep introduces major structural delays, meaning fraud analysts cannot catch high-value leakage before financial loss occurs.

### Goal of the Project
*   **Pipeline Rigor & Accuracy:** Clean and structure highly fragmented datasets, eliminating shadow duplicates, fixing system-generated time-travel logging faults, and resolving structural data types to ensure a clean relational data source.
*   **Proactive Threat Mitigation:** Isolate distinct behavior anomalies (temporal spikes, channel weaknesses, and targeted customer demographics) to replace rigid thresholds with a dynamic multi-vector fraud risk score.

### Walkthrough of Key Dashboard Modules
*   **1. Executive Fraud Overview:** Highlights high-level bank performance KPIs, tracking overall cross-channel exposure, global baseline fraud rates, and monthly transactional volume trends.
*   **2. Transaction Risk Analysis:** Evaluates transaction velocity, identifying high-risk heatmaps by comparing volume spikes against specific hours of the day and internal transaction types.
*   **3. Customer Risk Dashboard:** Segment risk vectors by user behaviors and demographics, isolating specific risk profiles by income levels, age bands, and gender traits.
*   **4. Branch & Geo Fraud Analysis:** Maps localized and regional exposure, isolating specific financial hotspots and high-risk branches within tier-1 cities.
*   **5. Card, ATM & Merchant Fraud:** Tracks failure logs and operational disputes, analyzing failed ATM withdrawal counts, card limit utilization, and high-risk merchant category chargeback rates.

## 6. Business Impact & Insights
*   **Data Integrity & Operational Efficiency:** Developed an automated data pipeline that fully standardized data types and resolved thousands of data anomalies, slashing manual data validation times.
*   **Temporal Risk Optimization:** Discovered an extensive fraud concentration between midnight and 4:00 AM, providing the empirical foundation to recommend dynamic late-night transaction friction (e.g., adaptive MFA) to disrupt automated attacks.
*   **Vulnerability Isolation:** Pinpointed that fraud exposure disproportionately targets the 60+ demographic and high-volume digital environments (NetBanking and Cards), driving the strategic rollout of targeted senior-citizen account holding periods and tokenized card safeguards.
*   **Preventative Control Transition:** Outlined a functional blueprint to transition from rigid, single-rule transaction limits to a composite statistical fraud risk score (evaluating amount Z-scores, hour weights, age segments, and chargeback metrics simultaneously), drastically maximizing detection accuracy while minimizing false-positive customer impact.

## 7. Dashboard Demo:

**[Click Here to Interact with the Live Power BI Dashboard](https://app.powerbi.com/view?r=eyJrIjoiNjgwZmMzMTQtMmJhMy00ZTllLWEyZjQtMjI1MDE0YjI3ZTYwIiwidCI6IjhlMjQ0OTAwLWJiZDQtNGNlMC1iNzlhLTQ4ZTMwYWRjMDFkNyJ9)**

(If the live link is unavailable, view the automated system demonstration below)

![Project Demo](https://github.com/chinmai-budati/Fintrust-Banking-Fraud-Detection/blob/main/Demo.gif)
