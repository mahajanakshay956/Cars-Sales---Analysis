# Cars-Sales---Analysis
This dataset contains 30,000 records of individuals and the cars they own, along with associated attributes such as manufacturing year, credit card type, and price. It can be used for data analysis, machine learning practice, preprocessing exercises, visualization projects, and statistical exploration.
📄 Overview

The Cars Dataset is a synthetic dataset containing detailed information about 30,000 individuals and the cars they own.
It is designed for data analysis, machine learning practice, exploratory data analysis (EDA), visualization, and teaching purposes.

This dataset includes demographic-like fields, vehicle characteristics, and financial details such as credit card type and vehicle price.

📁 File Information

File name: cars.csv
Total rows: 30,000
Total columns: 9
Format: CSV (Comma-Separated Values)

📊 Dataset Schema
| Column Name             | Data Type | Description                                     |
| ----------------------- | --------- | ----------------------------------------------- |
| **First Name**          | String    | Owner’s first name                              |
| **Last Name**           | String    | Owner’s last name                               |
| **Country**             | String    | Country of residence                            |
| **Car Brand**           | String    | Vehicle manufacturer (e.g., Ford, Audi, Nissan) |
| **Car Model**           | String    | Model of the vehicle                            |
| **Car Color**           | String    | Color of the vehicle                            |
| **Year of Manufacture** | Integer   | Year the vehicle was manufactured               |
| **Credit Card Type**    | String    | Type of credit card owned by the person         |
| **Price**               | Integer   | Price of the car (in USD)                       |

🔍 Data Summary

All 30,000 records are complete (no missing values).

Mix of categorical and numerical features:

7 categorical columns

2 numerical columns (Year of Manufacture, Price)

Data is clean and ready for analysis without preprocessing.

📌 Sample Data
First Name | Last Name | Country    | Car Brand | Car Model      | Car Color | Year | Credit Card Type | Price
----------------------------------------------------------------------------------------------------------------
Yetty      | Arghent   | Indonesia  | Ford      | Club Wagon     | Teal      | 1993 | mastercard        | 100327
Crystal    | Bosworth  | China      | Cadillac  | Escalade ESV   | Fuscia    | 2007 | mastercard        | 70719
Monro      | Houdhury  | Indonesia  | Mazda     | Miata MX-5     | Orange    | 2009 | maestro           | 91498

🎯 Potential Use Cases
📈 Data Analysis

Exploratory Data Analysis (EDA)

Summary statistics and trend identification

Categorical distribution analysis

🛠️ Data Engineering

ETL practice

Cleaning and preprocessing exercises

Data integration and transformation workflows

📊 Visualization Projects

Dashboards with Plotly / Power BI / Tableau

Price distribution charts

Brand popularity or color frequency charts

🧪 Example Code Snippets
Load the dataset
import pandas as pd
df = pd.read_csv("cars.csv")
df.head()

View basic statistics
df.describe()

Check value counts
df['Car Brand'].value_counts()

📦 Directory Structure (Recommended)
project/
│
├── data/
│   └── cars.csv
│
├── notebooks/
│   └── analysis.ipynb
│
├── README.md
└── requirements.txt

⚠️ Notes

Data is synthetic and does not represent real individuals.

Can be safely used for training, teaching, and testing ML models.
