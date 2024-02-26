# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output:
# Program:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
data = pd.read_csv("/content/SAMPLEIDS.csv")
data.head()
data = pd.get_dummies(data)
data.isnull().sum()
columns_with_null = data.columns[data.isnull().any()]
```
### VISUALIZATION:
```
import seaborn as sns
plt.figure(figsize=(10,10))
sns.barplot(columns_with_null)
plt.title("NULL VALUES")
plt.show()
```
### NULL IMPUTATION:
```
for column in columns_with_null:
    median = data[column].median()  
    data[column].fillna(median, inplace=True)
data.isnull().sum().sum()
```
## Result
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/9d18fbd1-e6d2-4c30-a294-701a9deb11c7)
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/de78ef37-d226-4aaf-9f01-5a46ff48571a)
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/729464f6-4d82-46c6-adbf-b52b1c797f03)

![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/d0071673-1f93-4bc5-92e5-e0ae583049c5)

          
