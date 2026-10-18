# Student ML Datasets for Practice

A clean, beginner-friendly collection of synthetic student datasets for practicing data analysis, regression, and classification in Python.

This repository contains six CSV datasets designed for learning machine learning concepts with realistic, classroom-style examples. The data focuses on student CGPA, IQ, placement outcomes, and salary/package trends, making it useful for teaching, experimentation, and portfolio projects.

## Why this repository?

These datasets are ideal for:

- Learning Python and Pandas
- Practicing Exploratory Data Analysis (EDA)
- Building Simple Linear Regression models
- Building Multiple Linear Regression models
- Training Classification models
- Comparing model behavior across small and medium-sized datasets
- Using datasets in Jupyter Notebook, Google Colab, Kaggle, or local Python environments

## Dataset Collection

| No. | Dataset | Rows | Features | ML Task |
|:---:|---|---:|---|---|
| 1 | `cgpa_package_100.csv` | 100 | `cgpa`, `package` | Simple Linear Regression |
| 2 | `cgpa_package_300.csv` | 300 | `cgpa`, `package` | Simple Linear Regression |
| 3 | `cgpa_iq_package_100.csv` | 100 | `cgpa`, `iq`, `package` | Multiple Linear Regression |
| 4 | `cgpa_iq_package_300.csv` | 300 | `cgpa`, `iq`, `package` | Multiple Linear Regression |
| 5 | `placement_yes_no_100.csv` | 100 | `cgpa`, `iq`, `placement` | Binary Classification |
| 6 | `placement_yes_no_300.csv` | 300 | `cgpa`, `iq`, `placement` | Binary Classification |

## Dataset descriptions

### 1) CGPA vs Package
This dataset contains a single feature (`cgpa`) and a target variable (`package`). It is suitable for learning how to model a relationship between a student’s academic performance and their offered package.

- Input feature: `cgpa`
- Target: `package`

### 2) CGPA, IQ, and Package
This dataset adds `iq` as an additional input feature, allowing learners to explore Multivariate Linear Regression.

- Input features: `cgpa`, `iq`
- Target: `package`

### 3) Placement Classification
This dataset uses `cgpa` and `iq` to predict whether a student is placed or not.

- Input features: `cgpa`, `iq`
- Target: `placement`
- Classes: `Yes`, `No`

## Repository structure

```text
.
├── README.md
├── cgpa_package_100.csv
├── cgpa_package_300.csv
├── cgpa_iq_package_100.csv
├── cgpa_iq_package_300.csv
├── placement_yes_no_100.csv
├── placement_yes_no_300.csv
├── get-quickly.md
├── Use-any-quickly
└── LICENSE (if present in your branch)
```

## Quick start

Install the required dependencies:

```bash
pip install pandas numpy scikit-learn
```

Load a dataset directly from GitHub:

```python
import pandas as pd

url = "https://raw.githubusercontent.com/CodeWithAli51/CodeWithAli51/main/cgpa_package_100.csv"
df = pd.read_csv(url)

print(df.head())
print(df.shape)
print(df.columns)
```

## Example: Exploratory Data Analysis

```python
import pandas as pd

url = "https://raw.githubusercontent.com/CodeWithAli51/CodeWithAli51/main/cgpa_iq_package_300.csv"
df = pd.read_csv(url)

print(df.head())
print(df.info())
print(df.describe())
print(df.isnull().sum())
```

## Example: Simple Linear Regression

```python
import pandas as pd
from sklearn.linear_model import LinearRegression

url = "https://raw.githubusercontent.com/CodeWithAli51/CodeWithAli51/main/cgpa_package_300.csv"
df = pd.read_csv(url)

X = df[["cgpa"]]
y = df["package"]

model = LinearRegression()
model.fit(X, y)

print("Coefficient:", model.coef_[0])
print("Intercept:", model.intercept_)
```

## Example: Multiple Linear Regression

```python
import pandas as pd
from sklearn.linear_model import LinearRegression

url = "https://raw.githubusercontent.com/CodeWithAli51/CodeWithAli51/main/cgpa_iq_package_300.csv"
df = pd.read_csv(url)

X = df[["cgpa", "iq"]]
y = df["package"]

model = LinearRegression()
model.fit(X, y)

print(model.coef_)
print(model.intercept_)
```

## Example: Classification

```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score

url = "https://raw.githubusercontent.com/CodeWithAli51/CodeWithAli51/main/placement_yes_no_100.csv"
df = pd.read_csv(url)

X = df[["cgpa", "iq"]]
y = df["placement"]

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

model = LogisticRegression(max_iter=1000)
model.fit(X_train, y_train)

predictions = model.predict(X_test)
print("Accuracy:", accuracy_score(y_test, predictions))
```

## Learning objectives

This repository helps learners practice:

- Data loading and cleaning
- Feature and target selection
- Exploratory Data Analysis (EDA)
- Linear Regression
- Multiple Regression
- Binary Classification
- Model evaluation and comparison

## Technologies used

- Python
- Pandas
- NumPy
- Scikit-learn
- Jupyter Notebook / Google Colab
- CSV-based dataset workflows

## Important disclaimer

All datasets in this repository are synthetic and created for educational and learning purposes only. They do not represent real students, verified salary data, or actual employment records.

Package values are illustrative numerical values and do not imply any real-world financial or job-market meaning. Placement labels are generated for practice and should not be treated as factual information.

## License and usage

These datasets are intended for educational use, experimentation, and personal learning projects. If you reuse or redistribute them, please keep the attribution and synthetic-data disclaimer.

## Contributing

Contributions, suggestions, and improvements are welcome. If you have ideas for additional educational datasets, better documentation, or more example notebooks, feel free to open an issue or submit a pull request.

## Support

If you find this repository useful, consider giving it a star on GitHub and sharing it with others learning data science and machine learning.

Happy learning! 🚀
