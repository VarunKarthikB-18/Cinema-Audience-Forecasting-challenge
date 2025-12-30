
🎬 Cinema Audience Forecasting Challenge — Machine Learning Model

This project predicts the daily audience count for partnered theaters using real-world booking and theater metadata. The goal is to support theaters with demand forecasting, seat allocation, and optimized scheduling.

The dataset comes from a Kaggle challenge: Cinema Audience Forecasting.

📌 Project Overview

This solution combines multiple data sources including:

Dataset	Purpose	Size
visits_df	Historical audience count	214,046 rows
booking_df	Online booking transactions	68,336 rows
cinepos_booking_df	Offline ticket sales	1,641,966 rows
theaters_df & cinepos_theaters_df	Theater location & type metadata	829 + 4,690 rows
date_df	Day-of-week calendar info	547 rows

This data was merged, aggregated, cleaned, and enriched with robust feature engineering, including:

Date-based features (month, week, day, quarter)

Weekend, holiday & seasonal indicators

Online vs offline booking indicators

Theater/Aggregate audience statistics

Ticket volume based categories

Encoded location and theater-type features

Final training dataset: 214,046 samples & 33 features

📊 Exploratory Data Findings

Key audience behavior insights:

Strong weekly seasonality → big jumps during weekends

Holiday release spikes → extreme peaks in mid-Dec 2023 & New Year

Evening peak bookings: highest 18:00–21:00 period

Online bookings surged after Nov 2023 platform ramp-up

Demand concentrated among top theaters and regions

Geographical clustering reveals deployment mainly within limited regional zones — helpful in adding location-driven demand signals.

🧠 Machine Learning Models Used

Three supervised regressors were trained and evaluated:

Model	R² Score (Validation)	MAE ↓
Gradient Boosting	~0.76	—
Random Forest	~0.81	—
Extra Trees Regressor	Best (~0.85)	Lowest Error

Extra Trees performed best in:

Capturing nonlinear patterns

Seasonal-demand variance

Feature-rich interactions

📌 Selected Final Model: ExtraTreesRegressor

120 trees

max_depth = 15

n_jobs = -1 for parallel execution

Also applied:

Standardization

PCA (95% variance retention) for experimental model path

Time-based train-validation split (last 60 days reserved)

🔍 Feature Importance

Top drivers of audience demand:

Historically observed theater_mean, area_mean

Seasonal + weekday features

Booking-based indicators (tickets_booked, has_tickets)

Theater category encodings

This indicates local performance history is highly predictive of future turnout.

📈 Final Results

Predictions were constrained:

≥ 0 (no negative audience)

≤ 300 (avoid impossible extreme outputs)

Submission file generated:

submission.csv
38062 predictions
All values valid


Example:

ID	Predicted Audience
book_00001_2024-03-01	27
book_00001_2024-03-02	39
book_00001_2024-03-03	41
🧩 Tech Stack
Component	Technology
Language	Python
Notebook Runtime	Kaggle
ML Libraries	scikit-learn, pandas, numpy, seaborn, matplotlib
Time-Series Analysis	statsmodels
🚀 Future Improvements

Add movie metadata (genre, cast, language) — currently missing from test data

Holiday/event schedule integration for finer spikes

Ensemble stacking with tuned GBM + Extra Trees

Experiment with Deep Learning (Temporal CNNs, LSTMs)

📁 Repository Files
📦 Cinema-Audience-Forecasting
 ├── 23f2001305-notebook-t3.ipynb
 ├── submission.csv
 ├── README.md   👈 (This document)

👤 Author

B. Varun Karthik
Machine Learning & Engineering
