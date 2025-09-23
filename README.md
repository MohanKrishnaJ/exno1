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

# Coding and Output
```py
import pandas as pd
import numpy as np
import seaborn as sns
data=pd.read_csv("SAMPLEIDS.csv")
data
```
<img width="1432" height="315" alt="image" src="https://github.com/user-attachments/assets/0ee021cc-e38a-419b-878c-1eb12f49fe5c" />



```py
data.head(5)
```
<img width="1349" height="814" alt="image" src="https://github.com/user-attachments/assets/f673c7cd-29bf-4064-823a-394d019719ac" />



```py
data.tail()
```
<img width="1321" height="280" alt="image" src="https://github.com/user-attachments/assets/20c256f5-fde7-45b8-87e2-4eadd04754f7" />



```py
data.isnull()
```
<img width="1123" height="797" alt="image" src="https://github.com/user-attachments/assets/22ad68d4-b486-4efa-8c12-b1aeb45223a7" />


```py
data.notnull()
```
<img width="1247" height="817" alt="image" src="https://github.com/user-attachments/assets/bb0fc28f-7ceb-4e97-898a-2945f377d16c" />


```py
data.isnull().sum()
```
<img width="599" height="593" alt="image" src="https://github.com/user-attachments/assets/4ceaeb0a-ee92-4543-9f9a-99ea819ccd2c" />


```py
data.isnull().any()
```
<img width="487" height="619" alt="image" src="https://github.com/user-attachments/assets/5f1453c4-c917-43a6-8f5d-fcde88e35278" />

```py
data.dropna(axis=0)
```
<img width="1340" height="574" alt="image" src="https://github.com/user-attachments/assets/6f7be262-145b-4bf6-8f6a-2abec938c2c3" />


```py
data.dropna(axis=1)
```
<img width="626" height="798" alt="image" src="https://github.com/user-attachments/assets/0ee3ac2e-6abc-4973-b7c2-58c39b6bb1ff" />



```py
data.fillna(0)
```
<img width="1360" height="815" alt="image" src="https://github.com/user-attachments/assets/745794a0-9790-4598-8d48-fd2b63c8269a" />



```py
data.fillna(method='ffill')
```
<img width="1348" height="809" alt="image" src="https://github.com/user-attachments/assets/ab5cba6a-333f-4872-b43e-ed507ef9f209" />


```py
data.fillna(method='bfill')
```
<img width="1333" height="809" alt="image" src="https://github.com/user-attachments/assets/c1dc2870-71a1-4b87-8b97-420e9d2000dc" />


```py
data.fillna({"REGNO":23002926,"NAME":"MOHAN"})
```
<img width="1367" height="813" alt="image" src="https://github.com/user-attachments/assets/93ccc33c-f808-43ac-9b17-cb0a2e54b974" />


```py
ir=pd.read_csv("iris.csv")
ir
```
<img width="996" height="647" alt="image" src="https://github.com/user-attachments/assets/689c848a-6a67-4e8c-a509-b400ce63246d" />



```py
ir.describe()
```
<img width="859" height="397" alt="image" src="https://github.com/user-attachments/assets/c6e784cf-d93a-4a5d-a097-e1276041a8a5" />



```py
sns.boxplot(x="sepal_width",data=ir)
```
<img width="986" height="744" alt="image" src="https://github.com/user-attachments/assets/ea81a6c2-452f-477f-af26-47baa02d3d0a" />

```
q1=ir.sepal_width.quantile(0.25)
q3=ir.sepal_width.quantile(0.75)
iqr=q3-q1
print(iqr)
```
<img width="497" height="55" alt="image" src="https://github.com/user-attachments/assets/38f06d43-ce59-4376-9c5c-fe2212da831b" />



```py
rid=ir[((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
rid['sepal_width']
```
<img width="365" height="277" alt="image" src="https://github.com/user-attachments/assets/fc9a674f-bc1e-40a6-b829-3b298f37f897" />



```py
delid=ir[~((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
delid
```
<img width="962" height="583" alt="image" src="https://github.com/user-attachments/assets/25879e96-7bf5-4b15-ba92-f3bbc77a6d1d" />


```py
sns.boxplot(x='sepal_width',data=delid)
```
<img width="900" height="749" alt="image" src="https://github.com/user-attachments/assets/4496a9eb-beba-4989-bb6b-655a85c4ff8b" />


# Result
Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method.
