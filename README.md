#  Data Cleaning & Preprocessing 
This code provides a comprehensive framework for performing Exploratory Data Analysis (EDA) on the Titanic dataset, focusing on identifying patterns, handling anomalies, and visualizing relationships to derive actionable insights.
# Data Cleaning Pipeline in Python
This repository contains a streamlined, modular script for preprocessing raw datasets using pandas and numpy. The pipeline automates the "grunt work" of data cleaning, ensuring consistency and readiness for Exploratory Data Analysis (EDA) or Machine Learning.
## 🚀 Features
The script executes a six-step cleaning process to transform "dirty" data into a structured format:
 1. **Data Ingestion:** Loads CSV files and provides immediate shape and metadata summaries.
 2. **Deduplication:** Identifies and removes exact row duplicates.
 3. **Column Management:** * Drops user-defined irrelevant columns.
   * Standardizes headers (lowercase, replaces spaces with underscores).
 4. **Missing Value Handling:**
   * **Pruning:** Removes columns with more than 70% missing data.
   * **Imputation:** Fills numerical gaps with the **median** and categorical gaps with the **mode**.
 5. **Type Correction:** Parses date strings into datetime objects and prepares numerical strings for calculation.
 6. **Format Standardization:** Cleans string white-spaces and maps inconsistent categorical labels (e.g., "M" → "Male").
## 🛠️ Usage
### Prerequisites
Ensure you have the required libraries installed:
```bash
pip install pandas numpy

```
### Configuration
Before running the script, update the following variables in the code:
 * pd.read_csv('your_dataset.csv'): Replace with your file path.
 * cols_to_drop: List any IDs or notes specific to your file.
 * threshold: Adjust the percentage for dropping sparse columns.
### Running the Script
Execute the script via terminal or your IDE:
```bash
python data_cleaning_script.py

```
## 📊 Pipeline Logic Summary
| Step | Action | Logic |
|---|---|---|
| **Duplicates** | drop_duplicates() | Keeps the first occurrence, removes subsequent copies. |
| **Nulls (Numerical)** | fillna(median) | Robust against outliers compared to the mean. |
| **Nulls (Categorical)** | fillna(mode) | Uses the most frequent value to maintain distribution. |
| **Headers** | snake_case | Ensures programmatically friendly column access. |
## 📝 Example Output
Upon completion, the script outputs a summary of the data shape and the first five rows of the cleaned DataFrame:
```text
Initial Shape: (1000, 15)
Shape after removing duplicates: (980, 15)
Data Cleaning Complete!
   age  gender  purchase_date  total_spent
0   25    Male     2023-01-01        150.5
1   34  Female     2023-01-02         89.0

```
