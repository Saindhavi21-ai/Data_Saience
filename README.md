# Healthcare Patient Dataset Analysis

## 1. Dataset Description

The **Healthcare Patient Dataset** contains health information of 43 patients. It includes demographic details, health indicators, and diagnosis information.

### Attributes

| Attribute      | Description                                 |
| -------------- | ------------------------------------------- |
| Patient_ID     | Unique identification number of the patient |
| Age            | Age of the patient                          |
| Gender         | Gender of the patient                       |
| Height         | Height of the patient                       |
| Weight         | Weight of the patient                       |
| Blood_Pressure | Blood pressure measurement                  |
| Blood_Sugar    | Blood sugar measurement                     |
| Diagnosis      | Health diagnosis of the patient             |

---

## 2. Objective

The objective of this analysis is to **preprocess and analyze healthcare patient data** so that it can be used effectively for further data analysis and machine learning applications.

The analysis includes:

1. Loading the dataset using Pandas.
2. Examining the dataset structure and identifying missing values.
3. Handling missing numerical values using median imputation and categorical values using mode imputation.
4. Encoding Gender and Diagnosis using Label Encoding.
5. Detecting abnormal values in Blood Pressure and Blood Sugar using box plots.
6. Normalizing numerical health indicators using Min-Max Scaling.
7. Creating a correlation matrix of numerical variables.
8. Saving the processed dataset as `healthcare_processed.csv`.

---

## 3. Tools Used

* **Python** – Programming language used for data analysis.
* **Jupyter Notebook / JupyterLab** – Environment used to execute the analysis.
* **Pandas** – Used for loading, cleaning, and manipulating the dataset.
* **Matplotlib** – Used for creating box plots and correlation matrix visualization.
* **Scikit-learn** – Used for Label Encoding and Min-Max Scaling.

### Libraries Used

```python
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.preprocessing import LabelEncoder, MinMaxScaler
```

---

## 4. Analysis Performed

### 4.1 Data Loading

The healthcare dataset is loaded using Pandas:

```python
df = pd.read_csv("Healthcare_Patient_Dataset.csv")
```

### 4.2 Dataset Examination

The structure of the dataset is examined using `df.info()` and missing values are identified using:

```python
df.isnull().sum()
```

The dataset contains missing values in **Gender, Weight, Blood_Pressure, and Blood_Sugar**.

### 4.3 Missing Value Handling

Missing numerical values are replaced with the **median** of their respective columns.

Missing categorical values are replaced with the **mode**.

### 4.4 Label Encoding

The categorical variables **Gender** and **Diagnosis** are converted into numerical values using `LabelEncoder`.

### 4.5 Outlier Detection

Box plots are created for **Blood Pressure** and **Blood Sugar** to identify abnormal or potentially outlying values.

### 4.6 Min-Max Scaling

The numerical health indicators **Age, Height, Weight, Blood_Pressure, and Blood_Sugar** are normalized using `MinMaxScaler`.

The values are transformed to a common range between **0 and 1**.

### 4.7 Correlation Analysis

A correlation matrix is created after preprocessing to identify relationships between the numerical variables.

The analysis shows a **strong positive correlation between Blood Pressure and Blood Sugar** in this dataset.

### 4.8 Saving the Processed Dataset

The processed dataset is saved as:

```text
healthcare_processed.csv
```

using:

```python
df.to_csv("healthcare_processed.csv", index=False)
```

---

## 5. Output

The analysis produces:

* Cleaned dataset with missing values handled
* Label-encoded Gender and Diagnosis
* Box plots for Blood Pressure and Blood Sugar
* Min-Max normalized numerical health indicators
* Correlation matrix
* Processed dataset saved as `healthcare_processed.csv`

---

## 6. Conclusion

The Healthcare Patient Dataset was successfully loaded, cleaned, transformed, and analyzed. Missing values were handled using median and mode imputation, categorical variables were encoded, abnormal values were examined using box plots, and numerical health indicators were normalized using Min-Max Scaling. A correlation matrix was also generated to understand relationships between variables. The processed dataset was finally saved as `healthcare_processed.csv` for further analysis or machine learning applications.
