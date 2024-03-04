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
```
NAME: Dhiyaneshwar P
REGNO: 212222110009
```
# Data cleaning:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
data = pd.read_csv("/content/SAMPLEIDS.csv")
data.head()
```
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/01915e09-ead0-4478-88ad-6fe7adf2180c)
```
data = pd.get_dummies(data)
data.isnull().sum()
```
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/d88c74e0-7a70-4027-86ad-6c6dc759e0d8)
```
columns_with_null = data.columns[data.isnull().any()]
import seaborn as sns
plt.figure(figsize=(10,10))
sns.barplot(columns_with_null)
plt.title("NULL VALUES")
plt.show()
```
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/4d152c8b-60c5-46c2-aa6a-30da738c81ca)
```
for column in columns_with_null:
    median = data[column].median()  
    data[column].fillna(median, inplace=True)
data.isnull().sum().sum()
```
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/278ecfdd-7b17-4d0c-bb69-f15f2c5456a5)
# IQR:
```
import pandas as pd
import seaborn as sns
ir = pd.read_csv("/content/iris (1).csv")
ir.head()
```
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/b9de16cb-6c9a-49e2-89d0-074ba9e96745)
```
ir.describe()
```
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/b462ec43-da0d-4cf6-89e9-1838b96af4d2)
```
sns.boxplot(x='sepal_width',data=ir)
```
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/ad8e055c-5a06-48bf-9b0d-cf1f4f1fd220)
```
c1=ir.sepal_width.quantile(0.25)
c3=ir.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)
```
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/d9c869bd-13c7-492d-8f47-c87a4ce0a58e)
```
rid=ir[((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']
```
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/31dab14e-e3c5-41cc-8859-ef3b564c7a28)
```
delid=ir[~((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
delid
```
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/c32cd0af-3849-4aff-9ec1-4fd3752bafb0)
```
sns.boxplot(x='sepal_width',data=delid)
```
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/8536882b-593a-4d3b-8f22-61d3dbdeb39c) 
# Z SCORE:
```
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
import scipy.stats as stats
dataset=pd.read_csv("/content/heights.csv")
dataset
```
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/b4da4bec-fe43-492e-98bb-b742f617ba26)
```
df = pd.read_csv("heights.csv")
q1 = df['height'].quantile(0.25)
q2 = df['height'].quantile(0.5)
q3 = df['height'].quantile(0.75)
```
```
iqr = q3-q1
iqr
```
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/c62f09b3-ff09-461a-aa95-dde57592652b)
```
low = q1 - 1.5*iqr
low
```
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/e3050fa8-d664-491d-83f6-fa8b03def67d)
```
high = q3 + 1.5*iqr
high
```
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/71092e0c-6ac6-4571-bc0b-c9b897ce8acd)
```
df1 = df[((df['height'] >=low)& (df['height'] <=high))]
df1
```
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/10a8917b-1a5d-4220-9c5e-90ba0249f456)
```
z = np.abs(stats.zscore(df['height']))
z
```
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/4f8abad2-0f9f-4f91-a021-fd11bae2275e)

## Result:

Thus the outliers are detected and removed in the given file and the final data set is saved into the file.

          
