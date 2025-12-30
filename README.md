# Cinema Audience Forecasting challenge

This repository contains a Jupyter notebook implementing an end-to-end baseline pipeline for predicting cinema audience counts from booking and point-of-sale (CinePOS) datasets.

Overview
- Objective: build reproducible baselines to forecast audience counts per show/date using available logs and theater metadata. The notebook documents data exploration, cleaning, feature engineering, baseline modeling, and evaluation.
- Notebook: `23f2001305-notebook-t32025 - ML.ipynb` (open in Jupyter to run and edit).

Data
- The analysis uses multiple CSV inputs (booking logs, visits, theaters, CinePOS bookings). These are merged to create a modeling table with temporal features (date, month, week, dayofweek, hour), theater features, and booking aggregates.

Key findings (summary)
- Strong weekly seasonality: clear weekend peaks versus weekday troughs.
- Time-of-day concentration: bookings and sales concentrate in evening hours (≈17:00–22:00).
- Demand concentration: a short list of theaters account for a large portion of volume, making theater-level aggregates predictive.

Modeling approach
- Baseline models demonstrated: tree-based regressors (e.g., GradientBoostingRegressor, ExtraTreesRegressor).
- Preprocessing: simple scaling and handling of missing theater/booking fields.
- Evaluation metric used in the notebook: Mean Absolute Error (MAE).

How to run locally
1. Create and activate a Python virtual environment (recommended):

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

2. Launch Jupyter Lab / Notebook and open the notebook:

```bash
jupyter lab
# or
jupyter notebook
```

Why the notebook may appear non-editable on GitHub
- GitHub renders notebooks as static pages by default. To edit the notebook interactively, open it in a local Jupyter server or use an online platform that supports notebooks (Binder, Colab, Codespaces).

Options I can implement next (pick one)
- Add a Binder badge and minimal `environment.yml` or `requirements.txt` to run the notebook in Binder.
- Create a Colab-ready copy (upload to Colab) and add a shareable link.
- Extract the notebook into a clean Python script (`scripts/train.py`) with a small CLI to reproduce preprocessing and training.
- Add a `LICENSE` file (MIT recommended) if you want the repo publicly reusable.

Contact
- Repo: https://github.com/VarunKarthikB-18/Cinema-Audience-Forecasting-challenge

If you'd like, I will now add a Binder configuration and badge so you can open and edit the notebook in the browser. Tell me to proceed or pick a different next step from the list above.
# Cinema Audience Forecasting challenge

Project: Cinema Audience Forecasting challenge — exploratory analysis and baseline forecasting models for predicting audience counts.

Files in this repository
- `23f2001305-notebook-t32025 - ML.ipynb` — Jupyter notebook with EDA, feature engineering and modeling.
- `requirements.txt` — Python package requirements to run the notebook.
- `.gitignore` — recommended ignores (virtualenvs, checkpoint files).

Quickstart (open the notebook locally)
1. Create and activate a virtual environment (recommended):

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

2. Start Jupyter Lab or Notebook and open the file:

```bash
jupyter lab
# or
jupyter notebook
```

Why the notebook might look non-editable
- GitHub displays notebooks as static rendered files (read-only). To edit cells, open the notebook in a local Jupyter server (see Quickstart above) or use an online environment that supports notebooks (Binder, Colab, or GitHub Codespaces).

Optional: Open in Binder
- Add a `binder` badge or create a `binder` configuration to run the notebook in the cloud without local setup.

Notes & next steps
- If you want, I can: add a LICENSE, convert the notebook to a clean `.py` script, create a Binder/Colab link, or extract runnable scripts from the notebook.

License
- Add a license file (e.g., `MIT`) if you want this project publicly reusable.

Contact
- Repo: https://github.com/VarunKarthikB-18/Cinema-Audience-Forecasting-challenge

