# 🦠 COVID-19 Data Analysis Project

### 📊 Overview
This project analyzes the **COVID-19 pandemic trends** using **Python** and **Jupyter Notebook**.  
The main objective is to explore and visualize confirmed, active, recovered, and death cases across Indian states, while handling missing and inconsistent data through proper cleaning techniques.

---

## 🧠 Objectives
- Clean and preprocess the COVID-19 dataset (remove null and duplicate records).  
- Perform **Exploratory Data Analysis (EDA)** using Pandas and Seaborn.  
- Visualize key trends such as confirmed, active, recovered, and death cases.  
- Identify the top 10 most affected states.  
- Study the correlation between recovery and vaccination rates.  

---

## 🧰 Tools & Technologies Used
| Tool / Library | Purpose |
|----------------|----------|
| **Python** | Main language for data analysis |
| **Jupyter Notebook** | Interactive code environment |
| **Pandas** | Data cleaning and manipulation |
| **NumPy** | Numerical computation |
| **Matplotlib & Seaborn** | Visualization libraries |
| **CSV File** | Dataset storage and input |

---

## 📂 Dataset Information
The dataset contains daily and cumulative COVID-19 records for Indian states.

| Column Name | Description |
|--------------|-------------|
| `Date` | Date of data entry |
| `State/UnionTerritory` | State or Union Territory name |
| `Confirmed` | Total confirmed cases |
| `Deaths` | Total deaths reported |
| `Cured` | Total recovered cases |
| `Active_Case` | Active cases on that date |


---

## 🔍 Project Workflow

### 1️⃣ Data Cleaning
- Dropped duplicate records using `drop_duplicates()`.  
- Removed the last 28 null rows with `iloc[:-28]`.  
- Filled missing numeric values (`Confirmed`, `Deaths`, `Cured`, `Active_Case`) with 0.  
- Converted `Date` to proper datetime format.  

```python
covid_df.drop_duplicates(inplace=True)
covid_df = covid_df.iloc[:-28]
covid_df[['Confirmed','Deaths','Cured','Active_Case']] = covid_df[['Confirmed','Deaths','Cured','Active_Case']].fillna(0)
covid_df['Date'] = pd.to_datetime(covid_df['Date'])
