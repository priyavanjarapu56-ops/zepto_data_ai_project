# zepto_data_ai_project
# Zepto AI/ML Engineering Capstone

## Project Overview

This project is an end-to-end AI/ML platform consisting of three connected capabilities:

1. **Data Pipeline** — scrapes raw book data, cleans it, converts and stores it in a relational SQLite database, and performs SQL queries.
2. **Analytics Pipeline** — profiles and cleans the Titanic dataset, performs exploratory data analysis, builds classification models, evaluates and tunes them, and performs a regression task.
3. **Support Assistant** — provides a grounded GenAI support assistant using Zepto policy information.

All three modules are contained in this single repository.

---

## Repository Structure

```text
zepto-ai-ml-project/
│
├── README.md
├── requirements.txt
│
├── data_pipeline/
│   ├── data_pipeline.ipynb
│   └── README.md
│
├── analytics/
│   ├── analytics.ipynb
│   ├── titanic.csv
│   └── README.md
│
└── support_assistant/
    ├── support_assistant.ipynb
    └── README.md
```

---

## Setup

This project uses one consolidated `requirements.txt` file for all three modules.

Install the required Python packages using:

```bash
pip install -r requirements.txt
```

The notebooks can also be run using Google Colab.

---

# Module 1 — Data Pipeline

Location:

```text
/data_pipeline
```

The data pipeline uses `books.toscrape.com` as the raw data source.

The pipeline performs the following steps:

```text
Raw Website
    ↓
Web Scraping
    ↓
Data Cleaning
    ↓
Data Conversion
    ↓
SQLite Relational Storage
    ↓
SQL Queries
    ↓
Query Results
```

The module uses Python scraping tools to collect book information, cleans the resulting data, converts the required fields, stores the data in SQLite, and performs SQL queries including filtering, sorting, aggregation-related exploration, and joins.

### How to run

Open:

```text
data_pipeline/data_pipeline.ipynb
```

Run the notebook from beginning to end.

---

# Module 2 — Analytics Pipeline

Location:

```text
/analytics
```

The analytics pipeline uses the Titanic dataset.

The workflow is:

```text
Titanic Dataset
    ↓
Data Profiling
    ↓
Missing-Value Handling
    ↓
Exploratory Data Analysis
    ↓
Visualization
    ↓
Train/Test Split
    ↓
Preprocessing Pipeline
    ↓
Classification Models
    ↓
Model Evaluation
    ↓
Hyperparameter Tuning
    ↓
Regression
    ↓
Saved Model Pipeline
```

The classification models include:

* Logistic Regression
* Decision Tree
* Random Forest

The module also includes imbalance handling, hyperparameter tuning, ROC/AUC evaluation, and a multivariate regression task.

The cleaned/offline Titanic dataset is stored as:

```text
analytics/titanic.csv
```

### How to run

Open:

```text
analytics/analytics.ipynb
```

Run the notebook from beginning to end.

---

# Module 3 — Support Assistant

Location:

```text
/support_assistant
```

The support assistant uses Zepto policy information as its knowledge source and provides grounded answers to customer support questions.

The workflow includes:

```text
Policy Documents
    ↓
Knowledge Preparation
    ↓
Search / Retrieval
    ↓
Relevant Policy Information
    ↓
Grounded Response
```

### How to run

Open:

```text
support_assistant/support_assistant.ipynb
```

Run the notebook from beginning to end and follow the setup instructions contained in the notebook.

---

## Design Decisions

### Data Pipeline

The data pipeline separates raw collection, cleaning, transformation, storage, and querying so that each stage can be inspected independently. SQLite is used as the relational storage layer.

### Analytics Pipeline

The analytics workflow uses one cleaned dataset throughout the EDA and modeling stages. Preprocessing for machine learning is performed through a scikit-learn pipeline so that transformations are learned from training data and applied consistently to test data.

### Support Assistant

The support assistant is designed around grounded responses so that answers are based on the provided Zepto policy information rather than unsupported information.

---

## Project Goal

The three modules demonstrate an end-to-end AI/ML workflow:

```text
Data Engineering
      ↓
Analytics & Machine Learning
      ↓
Grounded GenAI Application
```

Together they demonstrate how raw data can be collected and transformed, analyzed and modeled, and then used as part of an intelligent application.
