# 🧬 Cancer Data Analysis & Predictive Modeling

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=flat-square&logo=scipy&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)

An end-to-end Python project on **50,000 cancer patient records (2015–2024, 10 countries, 8 cancer types)**. It uses exploratory analysis, hypothesis testing and machine learning to study risk factors, cancer severity, treatment cost and survival.

---

## 🔑 Key Results at a Glance

| Question | Answer |
|---|---|
| Strongest drivers of cancer severity | **Smoking (r = 0.48)** and **Genetic Risk (r = 0.48)** |
| Can severity be predicted? | ✅ Yes. Random Forest **test R² = 0.78** (5-fold CV R² = 0.78) |
| Can survival years be predicted? | ❌ No. Test R² ≈ **0.00**: the features carry no signal for survival |
| Does higher treatment cost mean longer survival? | ❌ No. r ≈ 0.00, **p = 0.92** |
| Does genetic risk amplify the effect of smoking? | ❌ No. Interaction term **p = 0.63** |
| Share of patients diagnosed early (Stage 0–I) | **~40%**, from 38.4% (Lung) to 40.6% (Liver) |

---

## 🎯 Questions Explored

1. How are patients distributed by age, gender, country, cancer type and stage?
2. Which risk factors (genetic risk, smoking, alcohol, air pollution, obesity) are linked to **cancer severity**?
3. What share of each cancer type is diagnosed at an **early stage**?
4. Can **severity** and **survival years** be predicted with machine learning?
5. How does **treatment cost** vary across countries, age groups and genders?
6. Is higher treatment cost associated with **longer survival**?
7. Do higher cancer stages lead to **higher cost and shorter survival**?
8. Does **genetic risk amplify** the effect of smoking on severity?

---

## 💡 Key Insights

- 🚬 **Risk factors:** Smoking and genetic risk have the strongest link to severity. Air pollution (r = 0.37) and alcohol use (r = 0.36) are moderate. Obesity is weaker (r = 0.25), and age shows no link.
- 🌲 **Severity model:** A tuned Random Forest (RandomizedSearchCV, 5-fold CV) explains **78% of the variation** in severity on unseen data. Tuning cut the train/test gap from 0.97/0.78 to 0.91/0.78.
- ⏳ **Survival model:** The survival-years model scored a validation R² of **−0.005**, which is no better than predicting the average. The learning curve and near-zero correlations confirm that the dataset lacks the features needed to predict survival.
- 💵 **Treatment cost:** Average cost stays around **$52K–$53K** across countries, genders, age groups and stages, with no meaningful pattern.
- 🧪 **Statistics:** Pearson and Spearman tests both **failed to reject** the null hypothesis of no link between cost and survival. An OLS interaction model found both smoking and genetic risk significant (p < 0.001), but not their interaction.
- 🔍 **Data quality note:** Risk factors are uniformly spread on 0–10 scales, and cost and survival barely change by stage. These are signs that the dataset is likely **synthetic**, so the conclusions describe this dataset rather than real-world medicine.

---

## 🛠️ Tools & Techniques

| Area | Used |
|---|---|
| **Data handling** | Pandas, NumPy |
| **Visualization** | Matplotlib, Seaborn (KDE, histograms, heatmaps, regression plots) |
| **Statistics** | SciPy (Pearson, Spearman, linear regression), Statsmodels (OLS with interaction) |
| **Machine learning** | scikit-learn: Random Forest, RandomizedSearchCV, cross-validation, learning curves, feature importance |

---

## 🔄 Methodology

1. **Data understanding:** checked structure, data types and duplicates (none)
2. **Descriptive analysis:** distributions of age, gender, country, cancer type, stage and cost
3. **Risk-factor analysis:** per-factor regression slopes and correlation with severity
4. **Early-diagnosis analysis:** Stage 0–I share for each cancer type
5. **Predictive modeling:** Random Forest for severity and survival, with hyperparameter tuning
6. **Model validation:** 5-fold cross-validation and learning curves to diagnose over- and underfitting
7. **Hypothesis testing:** cost vs survival, stage vs cost/survival, genetic risk × smoking interaction

---

## 📁 Project Structure

```
Cancer-Data-Analysis/
│
├── Cancer Data  Analysis.ipynb   # Full analysis, charts and models
├── data/
│   └── Readme.md                 # How to download the dataset
├── requirements.txt
└── README.md
```

---

## 🚀 How to Run

```bash
pip install -r requirements.txt
```

1. Download the dataset from Kaggle (see [`data/Readme.md`](data/Readme.md)) and save it as `data/global_cancer_patients_2015_2024.csv`.
2. Open `Cancer Data  Analysis.ipynb` in Jupyter and run all cells.

---

## 📂 Dataset

**Global Cancer Patients (2015–2024)** by zahidmughal2343 on [Kaggle](https://www.kaggle.com/datasets/zahidmughal2343/global-cancer-patients-2015-2024). It has 50,000 rows and 15 columns: demographics, risk-factor scores, cancer type and stage, treatment cost, survival years and a severity score.

---

## ⚠️ Disclaimer

This is an educational data analysis project. The findings describe this dataset only and are **not medical advice or clinical conclusions**.

---

## 👩‍💻 Author

**Riya Yadav** | B.Tech, Production & Industrial Engineering, NIT Jamshedpur
[LinkedIn](https://www.linkedin.com/in/riya-yadav-2b5688378) · [GitHub](https://github.com/Riya-Yadav-Tech)
