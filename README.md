# Transactions-Fraud-Datasets
This project addresses transactional fraud using an unsupervised anomaly detection model, as the initial dataset lacked fraud labels. An IsolationForest algorithm identifies outliers based on engineered features like user spending patterns and transaction timing. The outcome is an actionable report prioritizing suspicious activity. 
Transactional Fraud Detection: An Unsupervised Anomaly Detection Project
This repository showcases an end-to-end data science project focused on identifying fraudulent transactions using unsupervised machine learning. The primary goal is to detect suspicious activity in a real-world, unlabeled financial dataset, moving beyond theoretical exercises to create a practical, actionable solution for minimizing financial losses and enhancing customer security.

The project simulates a common business scenario where explicit fraud labels are unavailable. It demonstrates a robust methodology for transforming raw, complex data into a powerful anomaly detection system, complete with automated reasoning and prioritized alerts for investigators.

Key Features:

Unsupervised Anomaly Detection: Implements an IsolationForest model to identify statistically rare and suspicious transactions without relying on pre-existing fraud labels. This approach is crucial for real-world scenarios where labeled data is often scarce or non-existent.





Advanced Feature Engineering: Creates meaningful, behavior-based features from raw data to uncover hidden patterns. This includes calculating user-specific spending baselines (

user_mean, user_std), standardizing transaction amounts (amount_z_score), and analyzing temporal patterns like transaction velocity and time of day (time_since_last_txn_hours, is_night).



End-to-End Data Processing: Includes a comprehensive data cleaning and preparation pipeline using pandas. The process addresses complex issues like mixed data types, inconsistent column naming, and accounting-style negative values (e.g., 

($77.00)) to ensure data integrity.





Actionable & Prioritized Reporting: The project culminates in an automatically generated, human-readable report that flags the top 5 most suspicious transactions. Crucially, the report provides automated reasoning for each flag, explaining 




why a transaction is considered an anomaly (e.g., "This amount is 3.0 standard deviations away from this user's typical spending.").



Stakeholder-Focused Communication: Delivers tailored visualizations and reports for different audiences:


Executive Summary: A high-level plot comparing normal vs. anomalous transactions to quickly convey the model's value.





Analyst Deep Dive: Comparative plots showing the distinct characteristics of anomalies, such as their amount distribution and tendency to occur at night.





Investigator's Report: A clear, prioritized text file designed for immediate action.



Project Phases: A Structured Approach
This project follows a structured, six-phase data analysis framework, demonstrating a systematic approach to problem-solving.


Ask: Defined the core business problem: minimizing financial losses from fraud by developing a predictive model to identify suspicious transactions in near real-time. The goals of key stakeholders—the financial institution, the fraud management team, and customers—were clearly outlined.






Prepare: Outlined the data requirements, sourcing data exclusively from three provided CSV files: transaction, user, and card data. Acknowledged the critical limitation of having no predefined "fraud" label, which pivoted the project from supervised classification to unsupervised anomaly detection.





Process: Executed a rigorous data cleaning process using Python and the pandas library. This involved standardizing column names, correcting data types by removing non-numeric characters, and accurately converting parenthetical notation for negative financial values into numeric formats. The separate datasets were then merged into a single, enriched DataFrame.





Analyze: Engineered new features to capture behavioral and temporal patterns relevant to fraud, such as Z-scores for transaction amounts and flags for late-night activity. An 


IsolationForest model was trained on these features to calculate an anomaly score for each transaction.



Share: Created compelling, audience-specific deliverables. This included a high-level visual summary for executives, detailed characteristic plots for analysts, and a prioritized, actionable report for fraud investigators explaining why each top anomaly was flagged.





Act: Provided a clear, multi-layered action plan based on the findings. Recommendations include immediate investigation of top-flagged transactions, deployment of the model as a real-time "Guardian" system, and the launch of smart customer alerts to verify moderately suspicious activity. Success measurement was defined through Key Performance Indicators (KPIs) like Fraud Detection Rate (FDR) and False Positive Rate (FPR).





Technical Stack
Language: Python

Libraries:

Data Manipulation & Analysis: pandas

Machine Learning: scikit-learn (specifically IsolationForest and StandardScaler)

Data Visualization: matplotlib, seaborn

Live Demo & Report
Explore the results of the analysis:

Comparison of Normal vs. Anomalous Transactions: See how the model distinguishes suspicious activity based on transaction amount and time of day.

Actionable Anomaly Report: View the final, prioritized report generated for the fraud investigation team, complete with automated reasoning for each flagged transaction.

