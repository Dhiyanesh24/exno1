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
## 1. Read and display dataframe:
```
import pandas as pd
df=pd.read_csv('/content/SAMPLEIDS.csv')
df
```
## Output:
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/c060f148-808c-4e17-8593-e2031310d3b1)
## 2. Display head:
```
df.head()
```
## Output:
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/78d2d734-750f-4623-9f8a-7ac9c8dd8374)
### 3. Display tail:
```
df.tail()
```
## Output:
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/951c54e1-7f77-4e21-8b71-2fc20a76504e)
## 4. Info from datagram:
```
df.info()
```
## Output:
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/e7456d09-befc-491f-9a54-1c64a6a06aca)
## 5. Describe about dataframe:
```
df.describe()
```
## Output:
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/b92e0b2c-4a70-4999-b4e9-880cab01f50e)
## 6.  Shape of the datafram:
```
df.shape
```
## Output:
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/fe762e19-d2c3-460a-84ef-27e28611d5d0)
## 7. Checking tha NUll values:
```
df.isnull().sum()
```
## Output:
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/0b8e68f4-a2fd-4a65-a567-5d9bd1341b15)
## 8. Drop the Null values:
```
x=df.dropna(how='any')
x
```
## Output:
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/1e2bd89e-b5b8-4373-8f9a-4944dd49b7e5)
## 9. Drop the Null values in Total:
```
tot=df.dropna(subset=['TOTAL'],how='any')
tot
```
## Output:
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/2c6240cb-e9b6-4576-bb9f-7874a27cf425)
## 10.  FIll the Null values:
```
df.fillna(0)
```
## Output:
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/78985b33-47aa-45de-a388-c3379d6bfa35)
## 11. Finding the mean value:
```
mn=df.TOTAL.mean()
mn
```
## Output:
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/6301b531-ab7a-42b4-8799-7a04c9005c04)
## 12. Final output:
```
for x in df.index:
  if df.loc[x,"AVG"]>100:
    df.drop(x,inplace=True)
df
```
## Output:
![image](https://github.com/Dhiyanesh24/exno1/assets/118362288/eafff9de-f98e-47a5-bb52-f91929171cb1)

# Result
          
