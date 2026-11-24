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

Crossvalidation ROC-AUC: 0.774

Selected threshold: 0.35

Test ROC-AUC: Approximately 0.79

Logistic Regression was selected because it achieved the highest cross-validation ROC-AUC among the compared models. The 0.35 threshold was selected using out-of- training predictions because it produced a higher F1-score than the 0.50 threshold.

Limitations

Model generalisation: Logistic Regression performed best on the data that we have. However, the performance of Logistic Regression may change when we apply it in clinics that have different patients, different appointment patterns or different data characteristics. The model is a tool that learns from the data we give it. It may not work exactly the same way in every clinic.

Limited dataset: The model is trained on the appointment records that we have. Therefore, the predictions of the model may not capture every behaviour or every situation. The model can only learn from what it sees. It may miss patterns that are not present in the current dataset.

Changing circumstances: Unexpected events such as illness, emergencies, transport problems or changes in the schedule can affect attendance. These events may not be predictable from the appointment details that we have. A patient can suddenly become ill. Lose a bus and the model cannot foresee these changes.

Project Structure


CareLoop-No-Show-Guard/

├── README.md

├── 01_ingest_clean.ipynb

├── rejected_rows.json

├── appointments_clean.csv

├── clinics_enriched.csv

├── load_data.sql

├── 02_queries.sql

├── 03_model.ipynb

├── test_risk_scores.csv

├── 04_genai.ipynb

├── notes_analysed.csv

├── task_4_4_crosstab.csv

├── task_4_4_merged.csv

└── data/
   
    ├── appointments.csv
    
    ├── clinics.csv
    
    └── followup_notes.csv

Tools and Technologies

Python

Pandas and NumPy

Scikit-learn

SQL / MySQL

Google Colab

Open-Meteo API

Gemini API

Pydantic
