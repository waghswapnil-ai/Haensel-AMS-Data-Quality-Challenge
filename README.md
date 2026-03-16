# Haensel AMS - Data Quality Challenge

## Overview
This repository contains my analysis for a marketing analytics data 
quality challenge. The objective was to identify and resolve data 
quality issues across 5 tables before answering the business questions.

## Repository Structure
```
Haensel-AMS-Data-Quality-Challenge/
├── Analysis_HaenselAMS_Data_Challenge.ipynb    ← main analysis notebook
├── challenge.db              ← SQLite database (all 5 tables)
├── challenge_db_create.sql   ← database schema reference
└── README.md
```

## Tables Analysed
| Table | Description |
|-------|-------------|
| conversions | Frontend conversion tracking |
| conversions_backend | Backend conversions (source of truth) |
| api_adwords_costs | Google Ads campaign costs and clicks |
| attribution_customer_journey | Session level IHC attribution |
| session_sources | User sessions by channel |

## How to Run

### Prerequisites
- Python 3.x
- Miniconda or Anaconda

### Setup
1. Clone the repository:
```bash
git clone https://github.com/waghswapnil-ai/Haensel-AMS-Data-Quality-Challenge.git
cd Haensel-AMS-Data-Quality-Challenge
```

2. Create and activate a conda environment:
```bash
conda create -n analytics_env python=3.11
conda activate analytics_env
```

3. Install required packages:
```bash
pip install jupyter pandas matplotlib
```

4. Launch Jupyter Notebook:
```bash
jupyter notebook
```

5. Open `Analysis_HaenselAMS_Data_Challenge.ipynb` and run all cells top to bottom

### Note
The `challenge.db` SQLite database is included in the repository — 
no additional database setup required. SQLite is built into Python 
and requires no separate installation.

## Questions Answered
1. Are the costs in api_adwords_costs fully covered in session_sources?
2. Are conversions in the conversions table stable over time?
3. Double check conversions table with backend — any issues?
4. Are attribution results consistent? Any ihc values that don't make sense?
5. Do we have an issue with channeling? Are sessions per channel stable?
6. Any other issues?

## Key Findings
- 13 data quality issues identified and resolved across 5 tables
- €9,868.27 revenue discrepancy found and corrected using backend
- 5 campaigns with 0% session coverage — €1,064.06 unattributable spend
- Social - Paid channel 100% untagged at campaign level
- DK market revenue likely recorded in DKK not EUR
- Full findings and recommendations in Analysis_HaenselAMS_Data_Challenge.ipynb

## Dependencies
| Package | Purpose |
|---------|---------|
| pandas | Data manipulation and analysis |
| matplotlib | Visualisations |
| sqlite3 | Database connection (built into Python) |
| jupyter | Notebook environment |
