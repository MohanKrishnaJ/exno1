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
## Data Cleaning
1) Read and Display DataFrame
   
```python
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
```
![image](https://github.com/KothaiKumar/exno1/assets/121215739/eefa705b-590d-4b36-a38d-7ea099202ad7)
```python
import pandas as pd
df=pd.read_csv('/content/SAMPLEIDS.csv')
print(df.info)
```
![image](https://github.com/KothaiKumar/exno1/assets/121215739/ef712919-f67d-4543-83ef-c63a92e71ade)
```python
import pandas as pd
import pandas as pd
df=pd.read_csv('/content/SAMPLEIDS.csv')
print(df.head(13))
```
![image](https://github.com/KothaiKumar/exno1/assets/121215739/a882940a-bfa4-4ae5-ab90-f0002b75ca23)

```python
import pandas as pd
print(df.tail(12))
```
![image](https://github.com/KothaiKumar/exno1/assets/121215739/74673a37-9acb-424f-b1cf-12abd324ad4d)
```python
import pandas as pd
print(df.describe)
```
![image](https://github.com/KothaiKumar/exno1/assets/121215739/18a79a6c-6055-42cd-94bb-de05cf841daf)
```python
df.isnull().sum()
```
![image](https://github.com/KothaiKumar/exno1/assets/121215739/98bde86e-2902-45be-9685-f101dbae81e0)
```python
df.nunique()
```
![image](https://github.com/KothaiKumar/exno1/assets/121215739/5466405b-031e-4555-9844-11404d23c695)
```python
df.TOTAL.fillna(mn,inplace=True)
df
```
![image](https://github.com/KothaiKumar/exno1/assets/121215739/dce7bddd-6669-4042-90cb-8f1bf2d054cb)
```python
min=df.M4.min()
min
```
![image](https://github.com/KothaiKumar/exno1/assets/121215739/91b68d21-9463-4193-a4f8-41e8cefebc71)
```python
df.M4.fillna(min,inplace=True)
df
```
![image](https://github.com/KothaiKumar/exno1/assets/121215739/1de88c1b-2d57-4e29-8b88-bd35827f2967)
```python
import pandas as pd
import seaborn as sns
age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
![image](https://github.com/KothaiKumar/exno1/assets/121215739/0f1d18d1-2f8b-4b94-9ebf-e0c576300e1d)
```python
sns.boxplot(data=af)
```
![image](https://github.com/KothaiKumar/exno1/assets/121215739/df1c3578-4602-4b7a-9871-472ba052a15a)
```python
sns.scatterplot(data=af)
```
![image](https://github.com/KothaiKumar/exno1/assets/121215739/ee447e3c-2f7c-418f-ab6a-f3ede4d46c6b)
```python
q1=af.quantile(0.25)
q2=af.quantile(0.50)
q3=af.quantile(0.75)
iqr=q3-q1
iqr
low=q1-1.5*iqr
low
high=q3+1.5*iqr
high
```
![image](https://github.com/KothaiKumar/exno1/assets/121215739/3a07c32f-78a1-489e-9ece-ac8cdb168133)
```python
af=af[((af>=low)&(af<=high))]
af
```
![image](https://github.com/KothaiKumar/exno1/assets/121215739/2ad72d61-0a47-47fe-b673-922655b29bf6)
```python
af.dropna()
```
![image](https://github.com/KothaiKumar/exno1/assets/121215739/41228ce8-6262-4cac-9d6f-549501bb2978)
```python
sns.boxplot(data=af)
```
![image](https://github.com/KothaiKumar/exno1/assets/121215739/8e450c1e-a26d-4ece-b236-da68c669a822)
```python
sns.scatterplot(data=af)
```
![image](https://github.com/KothaiKumar/exno1/assets/121215739/9baec287-e78c-4168-b4b2-c5005194aa8a)
```python
data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,102,105]
df=pd.DataFrame(data)
df
```

![image](https://github.com/KothaiKumar/exno1/assets/121215739/b85dc956-d02f-4e9e-8f80-0be022e04b89)
```python
import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
z
```
![image](https://github.com/KothaiKumar/exno1/assets/121215739/79c2692d-4bb4-4c25-b98b-f20288d68c63)

# Result
Thus, the program for data cleaning using python has executed successfully.
