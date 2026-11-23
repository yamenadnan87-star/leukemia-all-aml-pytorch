# Acute Leukemia (ALL vs. AML) Classification from Gene Expression Data

A **PyTorch** and **Scikit-learn** pipeline for classifying **Acute Lymphoblastic Leukemia (ALL)** vs. **Acute Myeloid Leukemia (AML)** from microarray gene expression data (Golub et al., 1999) using a strict **leakage-free** evaluation workflow.

> **Note:** Research/educational project only (not a clinical diagnostic tool). Raw dataset files are excluded.

## Key Highlights
* **Leakage-Free Preprocessing & CV:** Deterministic `clip` (`[20, 16000]`) + `log2` transform, with `VarianceThreshold(0.1)`, `SelectKBest(f_classif)`, and `StandardScaler` fitted strictly inside training folds under **5×5 Repeated Stratified K-Fold CV**.
* **Models & Benchmarking:** Compares a `PyTorch` `MLP` (`Linear` + `BatchNorm1d` + `ReLU` + `Dropout` with `Adam`) against `Logistic Regression`, linear `SVM`, and `Random Forest`.
* **Analysis & Ablations:** Includes PCA, Welch's t-test with Benjamini–Hochberg `FDR`, out-of-fold ROC/confusion matrix, gene-count ($k$) and architecture/dropout ablations, original Golub train/test split evaluation, and fold biomarker selection stability.

## Files
* `ITE_ANN601_yamenrostom_leukemia_ann_project_en.ipynb` — Complete notebook.
* `README.md` — Project documentation.
