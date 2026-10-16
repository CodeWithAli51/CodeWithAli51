## Hi there 👋


# 📊 Student Datasets for Machine Learning

A collection of synthetic student datasets created for practicing **Data Analysis, Linear Regression, Multiple Linear Regression, and Classification** using Python and Scikit-learn.

This repository contains datasets of different sizes (100 and 300 rows) to help students and beginners learn machine learning concepts through hands-on practice.

## 📁 Datasets Included

| No. | Dataset | Rows | Columns | ML Task |
|:---:|---|---:|---|---|
| 1 | `cgpa_package_100.csv` | 100 | CGPA, Package | Simple Linear Regression |
| 2 | `cgpa_package_300.csv` | 300 | CGPA, Package | Simple Linear Regression |
| 3 | `cgpa_iq_package_100.csv` | 100 | CGPA, IQ, Package | Multiple Linear Regression |
| 4 | `cgpa_iq_package_300.csv` | 300 | CGPA, IQ, Package | Multiple Linear Regression |
| 5 | `placement_yes_no_100.csv` | 100 | CGPA, IQ, Placement | Classification |
| 6 | `placement_yes_no_300.csv` | 300 | CGPA, IQ, Placement | Classification |

## 📝 Dataset Descriptions

### 1. CGPA and Package
Contains CGPA and package values for practicing Simple Linear Regression.

- **Input feature (X):** `cgpa`
- **Target variable (y):** `package`

### 2. CGPA, IQ and Package
Contains CGPA, IQ, and package values for practicing Multiple Linear Regression.

- **Input features (X):** `cgpa`, `iq`
- **Target variable (y):** `package`

### 3. Placement Prediction
Contains student CGPA, IQ, and placement status for practicing classification.

- **Input features (X):** `cgpa`, `iq`
- **Target variable (y):** `placement`
- **Classes:** `Yes`, `No`

## 🛠️ Technologies

- Python
- Pandas
- NumPy
- Scikit-learn
- KaggleHub
- Jupyter Notebook
- Google Colab
- Kaggle Notebooks

## 🚀 Load a Dataset Directly into a Pandas DataFrame

You can load any CSV file from the Kaggle version of this dataset directly into a Pandas DataFrame using KaggleHub.

### Step 1: Install the Required Library

```python
%pip install -q kagglehub[pandas-datasets]
```

### Step 2: Reusable KaggleHub Code

Use this boilerplate code in your Jupyter Notebook or other supported Python environment.

```python
import kagglehub
from kagglehub import KaggleDatasetAdapter

# Choose the CSV file you want to load
file_path = "cgpa_package_100.csv"

# Load the dataset into a Pandas DataFrame
df = kagglehub.load_dataset(
    KaggleDatasetAdapter.PANDAS,
    "YOUR_KAGGLE_USERNAME/YOUR_KAGGLE_DATASET_SLUG",
    file_path,
)

# Display the first five records
print("First 5 records:")
print(df.head())
```

**Before running:** Replace `YOUR_KAGGLE_USERNAME/YOUR_KAGGLE_DATASET_SLUG` with the actual identifier of your published Kaggle dataset.

### Step 3: Select Another Dataset

To load a different CSV from the same Kaggle dataset, change the `file_path` value.

```python
file_path = "cgpa_iq_package_300.csv"
```

Available filenames:

```text
cgpa_package_100.csv
cgpa_package_300.csv
cgpa_iq_package_100.csv
cgpa_iq_package_300.csv
placement_yes_no_100.csv
placement_yes_no_300.csv
```

The selected CSV must exist in the Kaggle dataset version being accessed.

### Step 4: Explore the Data

Once loaded, `df` is a regular Pandas DataFrame.

```python
# View the first five rows
df.head()

# Check the number of rows and columns
df.shape

# Display column names
df.columns

# Check data types and missing values
df.info()

# View descriptive statistics
df.describe()
```

## 🤖 Example Machine Learning Tasks

### Simple Linear Regression

Predict package using CGPA.

```python
from sklearn.linear_model import LinearRegression

X = df[["cgpa"]]
y = df["package"]

model = LinearRegression()
model.fit(X, y)

print("Coefficient:", model.coef_)
print("Intercept:", model.intercept_)
```

### Multiple Linear Regression

Predict package using CGPA and IQ.

```python
from sklearn.linear_model import LinearRegression

X = df[["cgpa", "iq"]]
y = df["package"]

model = LinearRegression()
model.fit(X, y)

print("Coefficients:", model.coef_)
print("Intercept:", model.intercept_)
```

### Classification

Predict whether a student is placed.

```python
from sklearn.linear_model import LogisticRegression

X = df[["cgpa", "iq"]]
y = df["placement"]

model = LogisticRegression()
model.fit(X, y)

print("Model trained successfully!")
```

For proper evaluation, split the data into training and testing sets before training your models.

## 🎯 Learning Objectives

- Understand independent and dependent variables.
- Practice Simple and Multiple Linear Regression.
- Understand classification using categorical target variables.
- Load CSV datasets directly into Pandas.
- Perform basic exploratory data analysis.
- Train and evaluate machine learning models.
- Compare results across datasets of different sizes.

## ⚠️ Disclaimer

All datasets in this repository are synthetically generated for educational and machine learning practice purposes. They do not contain real student information, verified salary data, or actual placement records.

Package values are illustrative numerical values without a specified currency unit. Placement labels are synthetic and should not be used to make real-world employment decisions.

## 📄 License and Usage

These datasets are intended for educational purposes, experimentation, and personal projects. If you redistribute them, please retain the attribution and synthetic-data disclaimer.

---

**If you find this repository useful, consider giving it a ⭐ on GitHub!**

Happy Learning and Machine Learning! 🚀
