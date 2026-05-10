# 🏠 Smart Locality Recommender System

## 📌 Overview

This project builds a **Smart Locality Recommendation System** that suggests the best places to live in Delhi based on multiple factors such as rent, safety, connectivity, and infrastructure.

It combines **data analysis, feature engineering, and machine learning** to evaluate and rank localities, helping users make better housing decisions.

---

## 🎯 Problem Statement

Choosing a suitable locality in a metro city like Delhi is complex due to multiple influencing factors such as affordability, safety, and accessibility.

This project aims to:

* Analyze locality data
* Identify key factors affecting livability
* Recommend the best localities based on user budget

---

## 📊 Dataset

A **custom synthetic dataset** was created to simulate real-world urban locality conditions in Delhi.

### 🔹 Key Details:

* 1000+ records
* 13 features
* Real Delhi locality names
* Generated using domain-based assumptions

### 🔹 Features:

* avg_rent
* distance_to_college
* metro_distance
* safety_score
* food_score
* hospital_count
* mall_count
* public_transport_score
* pollution_index
* internet_speed
* student_rating

### 🔹 Dataset Info:

* Total Rows: 1000
* Total Columns: 13
* No missing values

---

## 🔍 Exploratory Data Analysis (EDA)

* Performed statistical analysis and visualization
* Checked distributions of all features
* Analyzed relationships using correlation heatmap

### 📌 Key Insights:

* Most features show low correlation (due to synthetic nature)
* Safety and transport-related features influence livability
* Rent and distance vary significantly across localities

---

## ⚙️ Feature Engineering

To align data with real-world preferences:

* Converted features like rent, distance, and pollution into **scores**
* Ensured higher values represent better living conditions

### 🔹 Final Score Calculation:

A weighted scoring model was used:

* Rent → 20%
* Distance → 20%
* Metro → 15%
* Safety → 15%
* Food → 10%
* Transport → 10%
* Pollution → 10%

This produced a **final livability score** for each locality.

---

## 🤖 Model Building

### 🔹 Models Used:

* Logistic Regression
* Random Forest Classifier

### 🔹 Target Variable:

* recommended (1 = good locality, 0 = not recommended)

---

## 📈 Model Performance

### ✅ Random Forest Results:

* Accuracy: **92%**

### 🔹 Confusion Matrix:

[[90  7]
[ 9 94]]

### 🔹 Classification Metrics:

* Precision: 0.92
* Recall: 0.92
* F1-score: 0.92

---

## 🔥 Feature Importance

The most influential factors in determining locality quality:

1. Safety Score
2. Food Score
3. Public Transport Score
4. Metro Distance
5. Rent

---

## 🏆 Recommendation System

A function was developed to recommend the best localities based on user budget:

```python
def recommend_localities(df, budget):
    df_filtered = df[df['avg_rent'] <= budget]
    return df_filtered.sort_values(by='final_score', ascending=False).head(5)
```

### 🔹 Output:

Returns top 5 localities based on:

* Budget constraint
* Livability score

---

## 🚀 Technologies Used

* Python
* Pandas, NumPy
* Matplotlib, Seaborn
* Scikit-learn

---

## 💼 Key Highlights

* Built a **custom synthetic dataset** using domain knowledge
* Applied **feature engineering aligned with real-world logic**
* Developed a **machine learning classification model**
* Achieved **92% accuracy**
* Implemented a **recommendation system**

---

## 📌 Future Improvements

* Use real-world datasets (housing APIs, maps data)
* Add user preference weighting (e.g., safety vs rent priority)
* Deploy as a web application (Streamlit)

---


