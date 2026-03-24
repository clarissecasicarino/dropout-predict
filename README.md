# 🎓 Data-Driven Dropout Prediction for Virtual Learning Environments

> An XGBoost early-warning system that identifies at-risk students by Week 4 using Open University Learning Analytics Dataset (OULAD) behavioral data.

## 📌 Overview

Distance universities lose **40–90% of students to dropout**, costing U.S. institutions an estimated **$10.7 billion annually**. Yet the signals that precede withdrawal — missed assessments, declining engagement, low Virtual Learning Environment (VLE) activity — are already captured in every learning management system.

This project builds a machine learning pipeline that turns those signals into a **weekly risk-ranked advisor dashboard**, enabling targeted interventions before students disappear.

| Metric                        | Value        |
| ----------------------------- | ------------ |
| 🏆 XGBoost AUC                | **0.922**    |
| 🎯 Dropout Recall             | **74%**      |
| 👥 Students Analyzed          | **25,774**   |
| 💶 Estimated Savings / Cohort | **€375,000** |

## 🔍 Research Question

> Can weeks 1–4 VLE behavioral data (assessment submission patterns and click activity) predict student dropout with actionable accuracy for early intervention?

**Validated Hypothesis:** Students with `pass_rate_ge40 < 50%`, `on_time_rate < 70%`, and VLE clicks in the bottom quartile carry a **3× higher dropout probability** — confirmed at p < 0.001 across all statistical tests.

For more information, you can go and **download the report** `Carino_AYDST_Report.pdf` to guide your understanding on the model's results.

## 🗂️ Repository Structure

```
dropout-predict/
├── data/
│   ├── studentInfo.csv
│   ├── studentVle.csv
│   ├── studentAssessment.csv
│   ├── assessments.csv
│   ├── courses.csv
│   ├── studentRegistration.csv
│   └── vle.csv
├── .gitattributes
├── .gitignore
├── Carino_AYDST_Capstone_v1.ipynb
├── Carino_AYDST_Report.pdf
├── index.html
└── README.md
```

## 🚀 Getting Started

No local installation needed. This notebook runs entirely on **Google Colab**.

### Step 1 — Download the Dataset

Download the datasets from the `data/` folder in this repository.

| File                      | Description                                  |
| ------------------------- | -------------------------------------------- |
| `studentInfo.csv`         | Student demographics and final results       |
| `studentVle.csv`          | Virtual Learning Environment click logs      |
| `studentAssessment.csv`   | Assessment submission records and scores     |
| `assessments.csv`         | Assessment metadata (type, due date, weight) |
| `courses.csv`             | Course module and presentation details       |
| `studentRegistration.csv` | Enrollment and unregistration dates          |
| `vle.csv`                 | VLE material metadata (activity type, week)  |

### Step 2 — Add Files to Your Google Drive

Upload all 7 CSV files to the following path in **your own** Google Drive:

```
My Drive/
└── datasets/
    ├── studentInfo.csv
    ├── studentVle.csv
    ├── studentAssessment.csv
    ├── assessments.csv
    ├── courses.csv
    ├── studentRegistration.csv
    └── vle.csv
```

> ⚠️ **Important:** The folder must be named exactly `datasets` and placed directly inside `My Drive`. The notebook reads from this exact path:
>
> ```python
> folder = "/content/drive/MyDrive/datasets"
> ```

### Step 3 — Open & Run the Notebook

1. Open [`Carino_Applying_DS_Toolkit_Capstone.ipynb`](./Carino_Applying_DS_Toolkit_Capstone.ipynb) in Google Colab
2. When the first cell runs, you'll be prompted to mount your Google Drive — sign in with the account where you saved the dataset files
3. Run all cells in order: **`Runtime > Run all`**

> 💡 **Tip:** The notebook is fully self-contained. Each section includes markdown explanations alongside the code so you can follow the analysis end-to-end.

## 📦 Dataset

This project uses the **[Open University Learning Analytics Dataset (OULAD)](https://www.kaggle.com/datasets/anlgrbz/student-demographics-online-education-dataoulad/)**, covering 22 courses at the Open University UK (2013–2014).
