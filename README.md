# 🎗️ Breast Cancer Wisconsin — Random Forest Classifier

A machine learning pipeline for classifying breast tumors as **benign or malignant** using the [UCI Breast Cancer Wisconsin (Original) Dataset](https://archive.ics.uci.edu/dataset/15/breast+cancer+wisconsin+original).

---

## 📌 Project Overview

This project demonstrates a full supervised learning workflow:

- Fetching real-world clinical data via `ucimlrepo`
- Cleaning and imputing missing values
- Training a **Random Forest Classifier**
- Tuning hyperparameters with **GridSearchCV**
- Evaluating with confusion matrix, classification report, feature importance, and ROC curve

---

## 📂 Dataset

| Property | Details |
|---|---|
| Source | UCI ML Repository (ID: 15) |
| Samples | 699 |
| Features | 9 (e.g., Clump Thickness, Cell Size Uniformity) |
| Target | Class — `2` (Benign) → `0`, `4` (Malignant) → `1` |
| Missing Values | 16 in `Bare_nuclei` (imputed with median) |

---

## 🛠️ Tech Stack

- **Python 3**
- `ucimlrepo` — dataset fetching
- `pandas`, `numpy` — data manipulation
- `scikit-learn` — modelling, tuning, evaluation
- `matplotlib`, `seaborn` — visualization

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/your-username/breast-cancer-rf-classifier.git
cd breast-cancer-rf-classifier
```

### 2. Install dependencies

```bash
pip install ucimlrepo scikit-learn pandas numpy matplotlib seaborn
```

### 3. Run the notebook

Open `Breast_cancer_Dataset.ipynb` in Jupyter or Google Colab and run all cells.

> **Google Colab**: [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1rcG_FxQLip5dnigaU-PrU28ZpMd4YRC3)

---

## 🔬 Methodology

### 1. Data Preprocessing
- Loaded features (`X`) and labels (`y`) from UCI repository
- Filled 16 missing values in `Bare_nuclei` using **median imputation**
- Mapped class labels: `2 → 0` (benign), `4 → 1` (malignant)

### 2. Train/Test Split
- **80/20 split** with stratification to preserve class balance

### 3. Baseline Model
- `RandomForestClassifier` with default parameters
- Evaluated with classification report and confusion matrix

### 4. Hyperparameter Tuning
GridSearchCV over the following grid (5-fold CV, scored by F1):

| Parameter | Values Tried |
|---|---|
| `n_estimators` | 50, 100, 200 |
| `max_depth` | None, 5, 10 |
| `min_samples_split` | 2, 5 |
| `max_features` | `sqrt`, `log2` |

### 5. Evaluation & Visualization
- ✅ Confusion Matrix
- ✅ Classification Report (Precision, Recall, F1)
- ✅ Feature Importance bar chart
- ✅ ROC Curve with AUC score

---

## 📊 Results

| Metric | Score |
|---|---|
| ROC-AUC | ~0.99 |
| F1 (Malignant) | ~0.97+ |

> *Exact values may vary slightly due to randomness in tree splitting.*

---

## 📈 Visualizations

**Confusion Matrix** — shows counts of true vs. predicted labels.

**Feature Importances** — ranks the 9 clinical features by their contribution to the model.

**ROC Curve** — plots the trade-off between sensitivity and specificity.

---

## ⚠️ Disclaimer

This project is for **educational purposes only**. It is **not** intended for clinical use or medical diagnosis.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 🙏 Acknowledgements

- [UCI Machine Learning Repository](https://archive.ics.uci.edu/) for the dataset
- Dr. William H. Wolberg (University of Wisconsin) for the original data collection
