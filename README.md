# 🚗 Car Market Trends Analysis with CarDekho Data

> A Python-based data analysis project exploring used-car and two-wheeler price trends using a CarDekho dataset.

## 📌 About the Project

This project analyzes **301 used-vehicle listings**, including **200 cars and 101 two-wheelers**, to understand the factors that influence resale prices.

I created this project as a **DIY data analysis case study** using Python, Pandas, NumPy, Matplotlib, and Seaborn.

The analysis focuses on vehicle age, mileage, ownership history, fuel type, transmission, seller type, and differences between cars and two-wheelers.

**Author:** Muhammad Shafeeq

---

## 🎯 Questions Explored

The project answers **25 questions** about the used-vehicle market, including:

- How vehicle prices vary across the dataset
- How vehicle age affects resale value
- Whether mileage has a major impact on price
- How previous ownership affects resale value
- Which fuel types are most common
- Manual vs. automatic transmission trends
- Individual vs. dealer sellers
- Differences between cars and two-wheelers
- Which vehicles appear to have unusually high resale prices

📄 **Detailed answers:**  
[`CarDekho_Case_Study_Answers.md`](CarDekho_Case_Study_Answers.md)

---

## 🔎 Key Insights

### 📊 Dataset

- **301 total vehicle listings**
- **200 cars**
- **101 two-wheelers**
- Vehicle years range from **2003 to 2018**
- No missing values were found in the dataset

### 📉 Depreciation

Vehicle age showed the strongest relationship with depreciation:

| Factor | Correlation |
|---|---:|
| Vehicle Age | **0.85** |
| Mileage | **0.51** |
| Ownership | **0.22** |

This suggests that **vehicle age was a much stronger factor in resale value than mileage or ownership count** within this dataset.

### 🚘 Popular Vehicles

- **Most listed car:** Honda City — 26 listings
- **Most listed bike:** Royal Enfield Classic 350 — 7 listings

### ⚙️ Vehicle Characteristics

- **40** vehicles have automatic transmission
- Only **2** vehicles use CNG
- The dataset is mainly made up of **manual petrol and diesel vehicles**
- Around **96%** of listings are single-owner, first-hand vehicles

---

## 🧠 What I Learned

Through this project, I practiced:

- Data cleaning and preparation
- Exploratory Data Analysis (EDA)
- Working with Pandas DataFrames
- Statistical correlation analysis
- Data visualization
- Comparing different vehicle categories
- Extracting insights from real-world datasets
- Presenting analytical findings clearly

---

## 🛠️ Technologies Used

```text
Python
Pandas
NumPy
Matplotlib
Seaborn
Google Colab

