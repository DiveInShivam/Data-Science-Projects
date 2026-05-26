# 🎓 Student Placement Predictor

A Machine Learning project that predicts whether a student will get placed based on academic performance, work experience, and employability test scores.

This project demonstrates a complete **end-to-end data science workflow** including data analysis, preprocessing using pipelines, model training, and evaluation.

---

## 📌 Project Objective

The objective of this project is to build a predictive model that can determine a student's placement status based on various academic and personal attributes.

This helps in:

* Understanding key factors influencing placements
* Assisting students in improving their profiles
* Analyzing placement trends using data

---

## 📊 Dataset

Dataset used: **Campus Placement Dataset**

Features include:

| Feature  | Description              |
| -------- | ------------------------ |
| gender   | Gender of student        |
| ssc_p    | 10th percentage          |
| hsc_p    | 12th percentage          |
| degree_p | Degree percentage        |
| workex   | Work experience          |
| etest_p  | Employability test score |
| mba_p    | MBA percentage           |
| status   | Placement status         |

---

## ⚙️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook

---

## 🔬 Project Workflow

1. Data Collection
2. Data Exploration (EDA)
3. Data Preprocessing using Pipeline
4. Feature Encoding & Missing Value Handling
5. Train-Test Split
6. Model Training (Logistic Regression)
7. Model Evaluation

---

## 📈 Exploratory Data Analysis

Key insights:

* Students with **higher degree percentage** are more likely to get placed
* **Work experience significantly increases placement chances**
* Employability test scores strongly impact placement outcomes

---

## 🤖 Machine Learning Model

Model used:

**Logistic Regression**

### ⚙️ Preprocessing Approach

* Missing values handled using **SimpleImputer**
* Categorical features encoded using **OneHotEncoder**
* Entire workflow managed using **Pipeline and ColumnTransformer**

This ensures:

* No data leakage
* Clean and scalable preprocessing
* Industry-standard implementation

---

## 📊 Model Performance

### ✅ Accuracy:

**88.37%**

### 📋 Classification Report:

| Class          | Precision | Recall | F1-Score |
| -------------- | --------- | ------ | -------- |
| Not Placed (0) | 0.82      | 0.75   | 0.78     |
| Placed (1)     | 0.91      | 0.94   | 0.92     |

### 📌 Key Observations:

* Model performs **very well for placed students (Class 1)**
* Slightly lower recall for non-placed students due to class imbalance
* Overall model is **balanced and reliable**

---

## 📁 Project Structure

```
student-placement-predictor
│
├── data
│   └── Placement_Data_Full_Class.csv
│
├── notebook
│   └── placement_analysis.ipynb
│
├── models
│   └── placement_model.pkl
│
├── README.md
```

---

## 🚀 How to Run the Project

1. Clone the repository

```
git clone https://github.com/yourusername/student-placement-predictor.git
```

2. Install dependencies

```
pip install pandas numpy matplotlib seaborn scikit-learn
```

3. Run the notebook

```
jupyter notebook
```

---

## 💡 Key Learnings

* Built an end-to-end machine learning pipeline
* Learned handling missing data using imputation
* Applied feature encoding using OneHotEncoder
* Understood model evaluation using classification metrics
* Gained experience with real-world dataset

---

