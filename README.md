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

<a href="cars-dataset.csv">Download dataset Here</a>

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
- Exploratory Data Analysis (EDA)
- Summary statistics and trend identification
- Categorical distribution analysis

🛠️ Data Engineering

- ETL practice
- Cleaning and preprocessing exercises
- Data integration and transformation workflows

📊 Visualization Projects

- Dashboards with Plotly / Power BI / Tableau
- Price distribution charts
- Brand popularity or color frequency charts

🧪 Example Code Snippets

--Connect to Google Drive

from google.colab import drive
drive.mount('/content/drive')

--Load the file path -
cars_data = '/content/drive/MyDrive/Cars Dataset/cars.csv'

--import Libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

--Convert to dataframe
df_cars = pd.read_csv(cars_data)

df_cars.info()

df_cars.head(10)

--Bar Chart for Top 10 Car Brand
--Top 10 Car Brands
top_10_brands = df_cars['Car Brand'].value_counts().head(10)
#plot the Bar Chart
plt.figure(figsize=(12,8))
sns.barplot(x=top_10_brands.index, y=top_10_brands.values)
plt.title('Top 10 Car Brands')
plt.xlabel('Car Brand')
plt.ylabel('Count')

--Top 10 Countries
top_10_counties = df_cars['Country'].value_counts().head(10)

--Plot Top 10 Counties
plt.figure(figsize=(15,5))
top_10_counties.plot(kind = 'barh', color = 'red', edgecolor = 'black')
plt.title('Top 10 Countries')
plt.xlabel('Countries')
plt.ylabel('Count')


--Top 3 revenue genrating Brand
top_3_brand = df_cars.groupby('Car Brand')['Price'].sum().nlargest(3)
--Pie Chart
plt.figure(figsize=(5,5))
plt.pie(top_3_brand, labels = top_3_brand.index, autopct = '%1.1f%%', startangle = 90)


--Revenue by year
years_revenue = df_cars.groupby('Year of Manufacture')['Price'].sum()
sns.lineplot(x=years_revenue.index, y=years_revenue.values,marker='o', color='blue')
plt.title('Revenue by Year')
plt.xlabel('Year')
plt.ylabel('Revenue')

--Yearwise carcolorwise revenue stacked bar chart
year_brand_revenue = df_cars.groupby(['Year of Manufacture', 'Car Color'])['Price'].sum().unstack()
year_brand_revenue.plot(kind='bar', stacked=True, figsize=(16,10))
plt.title('Total Revenue by Year and Car Color')
plt.xlabel('Year of Manufacture')
plt.ylabel('Revenue')
plt.show()


--Donut chart for credit type
credit_type_counts = df_cars['Credit Card Type'].value_counts()
plt.figure(figsize=(7, 16))
plt.pie(credit_type_counts.values, labels = credit_type_counts.index, autopct = '%1.1f%%', startangle = 90)
center_circle = plt.Circle((0, 0), 0.70, fc='white')
fig = plt.gcf()
fig.gca().add_artist(center_circle)
plt.title('Credit Card Type Distribution')
plt.show()

--Top 10 country revenue generati g countries
country_revenue = df_cars.groupby('Country')['Price'].sum().head(10)
plt.figure(figsize=(10, 6))
sns.barplot(y=country_revenue.index, x=country_revenue.values, palette='cubehelix')
plt.title('Total Revenue by Country')
plt.ylabel('Country')
plt.xlabel('Revenue')
plt.xticks(rotation=90)

--Top 10 Selling car by color
top_10_color = df_cars['Car Color'].value_counts().head(10)
--plot
plt.figure(figsize=(12,8))
sns.barplot(x=top_10_color.index, y=top_10_color.values, palette= 'Set2')
plt.ylabel = ('Revenue')
plt.title('Top 10 Selling Car by Color')


⚠️ Notes

Data is synthetic and does not represent real individuals.

Can be safely used for training, teaching, and testing ML models.
