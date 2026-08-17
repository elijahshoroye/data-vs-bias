# Data Sources

This document records the external data sources used throughout the
Manchester United Premier League 2026/27 prediction project.

The purpose is to maintain transparency, reproducibility, and traceability
of the data used in the analysis and prediction models.

---

## Primary Data Sources

| Source | Data                         | Seasons         | Purpose                                |
| ------ | ---------------------------- | --------------- | -------------------------------------- |
| FBref  | Premier League league tables | 2010/11–2025/26 | Historical team performance            |
| FBref  | Home & away records          | 2010/11–2025/26 | Home advantage and team strength       |
| FBref  | Shooting statistics          | 2010/11–2025/26 | Attacking performance                  |
| FBref  | Goalkeeping statistics       | 2010/11–2025/26 | Defensive performance                  |
| FBref  | Miscellaneous statistics     | 2010/11–2025/26 | Additional team performance indicators |

---

## FBref

**Website:** https://fbref.com/

**Competition:** Premier League

**Purpose:** FBref is the primary historical data source for this project. It provides
team-level Premier League performance statistics including league standings,
results, goals, shooting, goalkeeping and other performance metrics.

### Initial reference

2023/24 Premier League statistics:

https://fbref.com/en/comps/9/2023-2024/2023-2024-Premier-League-Stats

---

## Data Collection Principles

1. Raw data will be preserved in its original form where possible.
2. Raw datasets will not be manually modified.
3. Data cleaning and transformation will be performed programmatically.
4. Derived variables will be documented where relevant.
5. Data sources will be recorded before being used in the final model.
6. Sources will be checked for licensing and redistribution restrictions
   before raw data is published publicly.

---

## Data Pipeline

The intended data workflow is:

Raw Data
→ Cleaning
→ Validation
→ Transformation
→ Analysis
→ Modelling
→ Visualisation

---

## Data Quality Notes

Data quality checks will include:

- Missing values
- Duplicate records
- Team-name inconsistencies
- Season naming inconsistencies
- Unexpected values
- Changes in statistical definitions
- Consistency between related variables

---

## Last Updated

**Date:** 17 August 2026

**Project:** Manchester United Premier League 2026/27 Prediction

**Author:** Elijah Shoroye
