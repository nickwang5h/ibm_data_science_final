---
marp: true
mermaid: true
theme: gaia
paginate: true
class:
  # - invert
style: |
  section {
    font-size: 16px;
  }
  h1 {
    color: #cc241d;
    font-size: 32px;
  }
  h2 {
    color: #98971a;
    font-size: 24px;
  }
  p {
    font-size: 16px;
    width: 50%;
  }
  .columns {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 1rem;
  }
---

# IBM Data Science Capstone Project

Cong Wang
2023-12-04

---

# Outline

- Executive Summary
- Introduction
- Methodology
- Results
- Conclusion
- Appendix

---

# Executive Summary

## Project Stages

1. **Data Gathering:**
2. **Data Cleaning and Transformation:**
3. **Exploratory Data Analysis:**
4. **Interactive Visual Data Exploration:**
5. **Predictive Analysis (Classification):**

## Project result

- Explored data through EDA.
- Conducted geospatial analysis and Created an interactive dashboard.
- Developed four ML models with **~83.33%** accuracy.
- Models tended to over-predict successful landings, indicating the need for more data.

---

# Introduction

## Background

SpaceX has disrupted the space industry by offering significantly lower launch costs ($62 million vs. $165 million USD), largely due to successful rocket stage recovery.

## Challenge

Space Y aims to compete with SpaceX and has tasked us with training a machine learning model to predict the success of the Falcon 9 first stage recovery.

## Objective

This project seeks to predict the success of SpaceX Falcon 9 first stage landings, enabling cost estimation and informed competition in the commercial space launch market.

---

# Section 1:

# Methodology

---

# Summary of Data Analysis Methodology

## Data Collection

<div class="columns">
<div>

- **SpaceX API & Wikipedia**: Combined data from SpaceX public API and SpaceX Wikipedia page.
- **GET requests**: Making GET requests to the SpaceX REST API.
- **Web Scraping**: Extracting additional data.

## Data Wrangling

- **Value Counts**: Applied `.value_counts()` to analyze the data.

## Exploratory Data Analysis (EDA)

- **SQL Queries**: Manipulated and evaluated the SpaceX dataset.
- **Pandas & Matplotlib**: Visualized relationships and patterns.
</div>
<div>

## Interactive Visual Analytics

- **Folium**: Performed geospatial analytics.
- **Plotly Dash**: Created an interactive dashboard.

## Data Modelling and Evaluation

- **Scikit-Learn**: Pre-processing and data splitting.
- **Model Training**: Employed classification models.
- **Hyperparameter Tuning**: Utilized GridSearchCV.
- **Model Assessment**:
  - Confusion matrices for model evaluation.
  - Accuracy assessment for each model.
  </div>
  </div>

---

# Data Collection

<div class="columns">
<div>
## SpaceX Public API

</div>
<div class="mermaid">
graph TD
    A[GET Request to SpaceX] --> B[Convert to JSON]
    B --> C[Load to Pandas]
    C --> D[Clean Data]
    D --> E[Retrieve Data]
    E --> F[Store in Dictionary]
    F --> G[Finalize DataFrame]
</div>

---

# Data Wrangling Process

1. **Data Loading and Inspection:**

   - Load the SpaceX dataset.
   - Inspect the dataset for structure and columns.

2. **Number of Launches on Each Site:**

   - Count the number of launches at each site using `.value_counts()` on 'LaunchSite'.

3. **Number and Occurrence of Each Orbit:**

   - Count the occurrences of each orbit type using `.value_counts()` on 'Orbit'.

4. **Number and Occurrence of Landing Outcome per Orbit Type:**

   - Filter the data for each orbit type and count landing outcomes within each subset.

5. **Create the Training Label 'class':**
   - Create a new 'class' column based on specified conditions:
     - If 'Mission Outcome' is True, set 'class' to 1.
     - For other cases, set 'class' to 0.

---

# Section 2:

# Insights drawn from EDA

---
