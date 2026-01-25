# Gym ML Performance — Predicting Top-Set e1RM

This project builds a master-ready applied ML pipeline to predict **top-set e1RM** from training context and workload proxies.

## Target
- **top_set_e1rm** using Epley: `e1rm = weight * (1 + reps/30)`

## Evaluation
- Primary: **MAE**
- Secondary: RMSE (reporting only)

## Repo structure
- `notebooks/` weekly experiments (Week 1–12)
- `src/` reusable feature + modeling code
- `reports/REPORT.md` seminar-style writeup
- `data/` local-only raw data (not in git)
- `figures/` saved charts

## Quickstart
```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter lab
