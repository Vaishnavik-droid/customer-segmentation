# Customer Segmentation Project - Context Checkpoint

**Project Status:** Preprocessing Complete (Encoding Finished)  
**Current Stage:** Ready for Feature Scaling and Clustering

---

# Project Overview

This project began as a traditional customer segmentation analysis using an Airbnb listings dataset. However, its scope has intentionally been expanded to simulate an industry-grade machine learning system rather than a notebook-only data analysis project.

The long-term objective is to build an end-to-end machine learning pipeline capable of assigning any new Airbnb listing to its most appropriate customer segment using the preprocessing pipeline and trained clustering model.

Rather than ending with cluster visualization, the final deliverable will be a deployable inference system that accepts listing information and predicts which customer segment the listing belongs to.

---

# Final Project Vision

```
New Airbnb Listing
        │
        ▼
Data Validation
        │
        ▼
Preprocessing Pipeline
        │
        ├── Cleaning
        ├── Feature Engineering
        ├── Encoding
        └── Scaling
        │
        ▼
Saved Clustering Model
        │
        ▼
Predicted Customer Segment
        │
        ▼
Business Interpretation
```

The completed system should function similarly to a production ML application, where a user can provide details of a new listing and receive the predicted market segment together with its business interpretation.

---

# Project Objectives

## Primary Objectives

- Perform comprehensive exploratory data analysis.
- Clean and preprocess the Airbnb dataset.
- Engineer meaningful business features.
- Build customer segments using unsupervised learning.
- Interpret each cluster from a business perspective.

## Extended Objectives

Beyond clustering, the project aims to demonstrate production-level machine learning engineering by developing:

- Modular preprocessing pipeline
- Reusable feature engineering module
- Saved preprocessing artifacts
- Saved clustering model
- Inference pipeline
- Listing segmentation prediction tool

This extension transforms the project from a standard analytics notebook into an end-to-end ML application.

---

# Dataset

The project uses the Airbnb Open Data dataset containing listing information such as:

- Property location
- Host information
- Pricing
- Booking characteristics
- Review statistics
- Availability
- House rules

---

# Work Completed

## 1. Data Cleaning

Completed.

Major tasks performed include:

- Removed unnecessary columns.
- Corrected inconsistent values.
- Fixed spelling inconsistencies.
- Handled missing values.
- Removed invalid observations.
- Standardized feature names.
- Verified dataset integrity.

---

## 2. Feature Engineering

Completed.

The following engineered feature was created:

### Property Age

Derived from the construction year to better represent property characteristics.

The original construction year feature was replaced with property age.

---

## 3. Missing Value Handling

Completed.

Missing observations were removed after evaluating their impact on the dataset.

Final dataset contains:

- No missing values
- No duplicate records
- Consistent feature types

---

## 4. Encoding

Completed.

### Binary Encoding

Applied to:

- host_identity_verified
- instant_bookable

Mapping:

- verified → 1
- unconfirmed → 0
- True → 1
- False → 0

---

### One-Hot Encoding

Applied to:

- neighbourhood group
- room type
- cancellation_policy

Before encoding, neighbourhood spelling inconsistencies were corrected:

- brookln → Brooklyn
- manhatan → Manhattan

All categorical information has been preserved without introducing artificial ordinal relationships.

---

## 5. NLP Planning

Unlike conventional customer segmentation projects, this project intentionally retains the `house_rules` feature.

The feature contains nearly unique textual entries and is therefore unsuitable for conventional One-Hot Encoding.

Instead, it will be incorporated in a later project phase using Natural Language Processing techniques.

Potential approaches include:

- TF-IDF
- Sentence Embeddings
- Semantic Similarity
- Text-based clustering features

This NLP extension is intended to demonstrate practical AI integration rather than treating free-text as a high-cardinality categorical feature.

---

# Current Dataset Status

Current preprocessing output contains:

### Numerical Features

- Continuous variables
- Engineered features
- Binary encoded features
- One-Hot encoded categorical features

### Text Feature

- house_rules (retained intentionally)

Dataset Validation:

- No missing values
- No duplicate records
- Successful encoding
- Ready for scaling

---

# Current Project Structure

```
Customer-Segmentation/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   ├── 01_preprocessing.ipynb
│   ├── 02_clustering.ipynb (planned)
│   └── 03_nlp_extension.ipynb (planned)
│
├── src/ (planned)
│   ├── preprocessing.py
│   ├── feature_engineering.py
│   ├── pipeline.py
│   ├── inference.py
│   └── predict.py
│
├── models/
│
├── docs/
│
└── app/ (planned)
```

---

# Notebook Philosophy

The notebooks are designed to be educational and well-documented.

They explain:

- Why each preprocessing decision was made.
- Business reasoning behind feature engineering.
- Data validation.
- Visual analysis.
- Model interpretation.

Implementation simplicity is prioritized inside notebooks to maximize readability.

---

# Production Pipeline Philosophy

The production implementation will not reuse notebook code directly.

Instead, all preprocessing logic will later be rewritten into reusable modules inside the `src/` directory using Scikit-learn components.

Planned technologies include:

- ColumnTransformer
- OneHotEncoder
- StandardScaler
- Pipeline
- Joblib

The objective is to ensure that every new listing undergoes the exact same preprocessing steps as the training data before prediction.

---

# Planned Pipeline

```
Input Listing
      │
      ▼
Preprocessing Module
      │
      ▼
Feature Engineering
      │
      ▼
Encoder
      │
      ▼
Scaler
      │
      ▼
Saved Clustering Model
      │
      ▼
Predicted Segment
```

The preprocessing notebook serves as documentation of the methodology, while the production pipeline will provide reusable, deployment-ready implementations of the same logic.

---

# Remaining Roadmap

## Phase 1 — Preprocessing

- [x] Cleaning
- [x] Feature Engineering
- [x] Missing Value Handling
- [x] Encoding
- [ ] Save processed datasets

---

## Phase 2 — Clustering

- Feature Scaling
- Elbow Method
- Silhouette Analysis
- K-Means Clustering
- Hierarchical Clustering
- DBSCAN
- Cluster Comparison
- Cluster Selection
- Business Interpretation

---

## Phase 3 — NLP Enhancement

- Text preprocessing
- Feature extraction
- Semantic embeddings
- Integration with structured features
- Evaluate impact on segmentation

---

## Phase 4 — Production ML Pipeline

Develop reusable modules:

- preprocessing.py
- feature_engineering.py
- pipeline.py
- inference.py
- predict.py

Persist preprocessing objects and clustering model using Joblib.

---

## Phase 5 — Listing Segmentation Tool

Develop a production-style application where users can enter details of a new Airbnb listing.

The application will:

1. Validate the input.
2. Apply the preprocessing pipeline.
3. Perform feature engineering.
4. Encode categorical variables.
5. Scale numerical features.
6. Load the saved clustering model.
7. Predict the customer segment.
8. Display an interpretable business description of the predicted segment.

---

# Project Goal

The final deliverable is not simply a clustering notebook.

The objective is to demonstrate an end-to-end machine learning workflow that combines:

- Data Analytics
- Feature Engineering
- Unsupervised Machine Learning
- Natural Language Processing
- Modular Software Engineering
- Production-Oriented ML Pipelines

The completed project should resemble the architecture and workflow of a real-world machine learning system while remaining fully reproducible, well-documented, and suitable for an internship portfolio.