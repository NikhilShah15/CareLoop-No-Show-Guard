CareLoop Clinics — No-Show Guard

GitHub Repository: [Paste your public GitHub repository URL here]

Project Overview

CareLoop Clinics. No-Show Guard is a data analysis and machine learning project. It focuses on understanding and predicting missed appointments. The project combines data cleaning, SQL analysis, machine learning and AI-assisted follow-up note analysis. This helps clinics spot appointments at risk of becoming no-shows.

Key Findings

Part 1 — Data Foundations: Cleaned 1,020 raw appointment records into 990 usable records, identifying 218 no-shows.
Part 2 — SQL Analysis: Found that appointments booked 31 or more days in advance had the highest no-show rate of 60.5%.
Part 3 — Machine Learning: Logistic Regression achieved a cross-validation ROC-AUC of 0.774, with a selected risk threshold of 0.35.
Part 4 — GenAI Analysis: Analysed 10 follow-up notes, with 9 valid results and 1 blank note skipped.

Business Recommendation

CareLoop should concentrate its follow‑up efforts on appointments that are booked a time before. For example, appointments with a time of 31 days or more had a 60.5 percent no‑show rate. In contrast, appointments booked 1 to 7 days ahead had a 16.2 percent no‑show rate. Among 990 cleaned appointments, 218, which's 22.0 percent, were missed. This shows that no‑shows are a problem for the clinics. To help find appointments that need attention, the Logistic Regression model was chosen. This model had a cross‑validation ROC‑AUC of 0.774 and a risk threshold of 0.35. With this model, the front desk can prioritise calls to patients who're more likely to miss their appointments. In addition, the analysis of 10 follow‑up notes, of which 9 were classified correctly, gives insight into reasons for missed appointments. CareLoop can use these findings to prioritise follow‑ups and to better understand why patients miss appointments.

Machine Learning Model

Selected Model: Logistic Regression

Why it was selected:
It achieved the highest cross-validation ROC-AUC among the compared models.
Its cross-validation ROC-AUC was 0.774.
It provided a useful balance of interpretability and predictive performance.
Selected Risk Threshold: 0.35
The threshold was selected using out-of-fold predictions on the training data. It produced a higher F1-score than the 0.50 threshold, making it more suitable for identifying appointments that may need follow-up.

Limitations

Model generalisation: Logistic Regression performed best on the data that we have. However, the performance of Logistic Regression may change when we apply it in clinics that have different patients, different appointment patterns or different data characteristics. The model is a tool that learns from the data we give it. It may not work exactly the same way in every clinic.

Limited dataset: The model is trained on the appointment records that we have. Therefore, the predictions of the model may not capture every behaviour or every situation. The model can only learn from what it sees. It may miss patterns that are not present in the current dataset.

Changing circumstances: Unexpected events such as illness, emergencies, transport problems or changes in the schedule can affect attendance. These events may not be predictable from the appointment details that we have. A patient can suddenly become ill. Lose a bus and the model cannot foresee these changes.

Project Structure

01_ingest_clean.ipynb — Part 1: Python data ingestion and cleaning.
rejected_rows.json — Rejected records from initial ingestion.
appointments_clean.csv — Cleaned appointment dataset.
clinics_enriched.csv — Clinic data enriched with weather information.
load_data.sql — SQL insert statements for database loading.
02_queries.sql — Part 2: SQL analysis queries.
03_model.ipynb — Part 3: Machine learning workflow.
test_risk_scores.csv — Test-set risk predictions.
04_genai.ipynb — Part 4: GenAI follow-up note analysis.
notes_analysed.csv — Validated follow-up note analysis results.
data/ — Original appointment, clinic and follow-up note datasets.

Tools and Technologies

Python
Pandas and NumPy
Scikit-learn
SQL / MySQL
Google Colab
Open-Meteo API
Gemini API
Pydantic



The final model was evaluated on the held-out test set, achieving an ROC-AUC of approximately 0.79.
