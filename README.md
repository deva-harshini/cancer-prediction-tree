# Patient Classification & Radiation Data Analysis

This project builds a machine learning pipeline to classify patient outcomes based on protein concentration levels (TAU) and Radiation Therapy doses (IR). It utilizes a Logistic Regression model, evaluates its performance using ROC/AUC metrics, and provides a SQLite database system to log new patient records.

---

## 🛠️ Features

* **Data Preprocessing:** Cleans and splits clinical data into training and testing sets.
* **Predictive Modeling:** Train a `Logistic Regression` classifier to predict patient status.
* **Performance Evaluation:** Generates Receiver Operating Characteristic (ROC) curves and computes the Area Under the Curve (AUC) score.
* **Database Integration:** A localized SQLite3 interface to drop, create, populate, and query patient clinical records.

---

## 📦 Prerequisites & Installation

Ensure you have Python installed. You can install all the required library dependencies using `pip`:

```bash
pip install pandas numpy scikit-learn matplotlib

```

> **Note:** This project utilizes `sqlite3`, which comes built-in with standard Python installations.

---

## 🚀 How to Run

1. Place your dataset in the same directory as the script and name it `data.csv`.
2. Ensure your `data.csv` contains at least three columns representing: **TAU (nM)**, **IR (Gy)**, and the **Target Status** (binary classification).
3. Run the Python script:

```bash
python main.py

```

---

## 📊 Model & Workflow Details

### 1. Feature Selection

The model uses two primary biological and clinical indicators:

* `TAU (nM)`: Tau protein concentration levels.
* `IR (Gy)`: Ionizing Radiation dosage in Grays.

### 2. Machine Learning Pipeline

* **Train-Test Split:** The dataset is split into **80% training** and **20% testing** data.
* **Model Configuration:** A `Logistic Regression` model is utilized with an `lbfgs` solver.
* **Metrics Generated:** * Accuracy Score
* ROC Curve (Sensitivity vs. Specificity)
* AUC Score



### 3. SQLite Database Schema

The script automatically sets up a SQLite database file named `record.db`. It manages a `patient` table with the following schema:

| Column Name | Data Type | Description |
| --- | --- | --- |
| `id` | INTEGER | Primary Key (Auto-Incremented) |
| `name` | TEXT | Patient's Name |
| `status` | INTEGER | Diagnostic Status (0 or 1) |
| `value` | INTEGER | TAU Value measurements |
| `radiation` | INTEGER | Radiation dose administered |

---

## 📝 Script Interaction Notice

Upon running the script, the terminal will prompt you to manually log a new entry into the patient database:

```text
Enter the name: John Doe
Enter the status: 1
Enter the value: 15
Enter the radiation: 4

```

After entry, the script will output the full updated database table layout directly to your console.
