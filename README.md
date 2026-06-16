# WFH Burnout Predictor

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/simonemastria/WFH-Burnout-Predictor/blob/main/burnout_prediction.ipynb)

This Machine Learning and Data Mining project predicts work-from-home burnout from daily behavioral indicators such as working hours, screen time, meetings, breaks, after-hours work, sleep and task completion.

The project follows the CRISP-DM process:

1. Business Understanding
2. Data Understanding
3. Data Preparation
4. Modeling
5. Evaluation
6. Deployment discussion

## Dataset

The dataset is the public Kaggle **Work From Home Employee Burnout Dataset**:

https://www.kaggle.com/datasets/sonalshinde123/work-from-home-employee-burnout-dataset

Local copy:

```text
data/burnout_dataset.csv
```

The dataset contains:

- 1,800 observations;
- 180 users;
- 10 records per user;
- no missing values;
- a continuous target, `burnout_score`;
- a categorical target, `burnout_risk`.

## Project Structure

```text
WFH-Burnout-Predictor/
├── burnout_prediction.ipynb              # Main executable notebook
├── data/
│   └── burnout_dataset.csv
├── Report/
│   ├── IEEEtran.cls
│   ├── report_wfh_burnout.tex
│   ├── report_wfh_burnout.pdf
│   └── presentation_wfh_burnout.pdf
├── requirements.txt
└── README.md
```

## Modeling Strategy

The primary task is regression on `burnout_score`. Classification of `burnout_risk` is treated as secondary because the `High` class is rare.

The notebook includes:

- data quality checks;
- target distribution analysis;
- outlier analysis;
- feature engineering;
- grouped train/test split by `user_id`;
- leakage-safe preprocessing pipelines;
- baseline models;
- regression and classification models;
- hyperparameter tuning;
- sensitivity analysis without `task_completion_rate`;
- feature importance;
- fairness and ethics checks;
- deployment plan.

## Main Results

The tuned Random Forest regression model achieves about:

- Test MAE: 4.88
- Test RMSE: 6.21
- Test R2: 0.936

The sensitivity analysis without `task_completion_rate` is included because that feature is highly correlated with the target and must be interpreted carefully.

## Run Locally

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook burnout_prediction.ipynb
```

## Outputs

- Executable notebook: `burnout_prediction.ipynb`
- IEEE-style report: `Report/report_wfh_burnout.pdf`
- Presentation: `Report/presentation_wfh_burnout.pdf`

## Author

Simone Mastria  
University of Bologna  
Machine Learning and Data Mining, Module 2
