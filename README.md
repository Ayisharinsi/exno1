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
```
import pandas as pd
import numpy as np
import seaborn as sns
import os 
df=pd.read_csv("SAMPLEIDS.csv")
df
```
![image](https://github.com/user-attachments/assets/0708a1ae-c7cc-4dc3-8eb7-6ce9291e691f)
```
df.isnull().sum()
```
![image](https://github.com/user-attachments/assets/17abf1d1-51bb-49f0-9a77-2cc06eea8840)
```
df.isnull().any()
```
![image](https://github.com/user-attachments/assets/0b714954-f6c3-4892-9b05-12bcfa91406d)
```
df.dropna()
```
![image](https://github.com/user-attachments/assets/f083cc0d-051f-4189-ad27-082b1246caa1)
```
df.fillna(0)
```
![image](https://github.com/user-attachments/assets/cfceedd9-0706-44eb-a377-bcfadea004cc)
```
df.fillna(method = 'ffill')
```
![image](https://github.com/user-attachments/assets/a22e7caf-2566-429f-88c4-37ab47414c19)
```
df.fillna(method = 'bfill')
```
![image](https://github.com/user-attachments/assets/b54d36a8-6771-402f-bbe9-594e4aed191a)
```
df_dropped = df.dropna()
df_dropped
```
![image](https://github.com/user-attachments/assets/95c9b8b9-2cbb-4b78-a0a6-052a393c6935)
```
df.fillna({'GENDER':'FEMALE','NAME':'PRIYU','ADDRESS':'POONAMALEE','M1':98,'M2':87,'M3':76,'M4':92,'TOTAL':305,'AVG':89.999999})
```
![image](https://github.com/user-attachments/assets/70bda816-320f-49fc-ad14-00e346b83484)
```
ir=pd.read_csv('iris.csv')
ir
```
![image](https://github.com/user-attachments/assets/48ce2758-5329-42f9-bd75-81e5517a4be5)
```
ir.describe()
```
![image](https://github.com/user-attachments/assets/2fb26813-0e44-4e5d-9ae8-69bee979a6e0)
```
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)
```
![image](https://github.com/user-attachments/assets/fafb60b2-1980-492e-83dd-250bcfed8225)

![image](https://github.com/user-attachments/assets/a753dd90-e4bc-440e-b861-4fd93e46e7ba)
![image](https://github.com/user-attachments/assets/cdb1c820-2030-4818-9e3d-9a997184e0d9)
![image](https://github.com/user-attachments/assets/65ef7c81-009c-49d0-91c7-007f8db16d19)
```
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np
import scipy.stats as stats
dataset=pd.read_csv("heights.csv")
dataset
```
![image](https://github.com/user-attachments/assets/7ea299f4-0441-4294-bf33-4d64520ca14f)

```
df = pd.read_csv("heights.csv")
q1 = df['height'].quantile(0.25)
q2 = df['height'].quantile(0.5)
q3 = df['height'].quantile(0.75)
iqr = q3-q1
iqr
```
![image](https://github.com/user-attachments/assets/80cadd71-4a3e-4245-9bb1-c4223c453f58)

![image](https://github.com/user-attachments/assets/61f43aee-0567-45ef-a83d-450328cf6ec1)
```
z = np.abs(stats.zscore(df['height']))
z

```
![image](https://github.com/user-attachments/assets/ba8c9480-9cd4-4a45-9546-03e8546d2a62)
```
df1 = df[z<3]
df1
```
![image](https://github.com/user-attachments/assets/b57d33fd-d6f0-4741-964e-8efdb33af6f3)
```
# Result
Thus to read the given data and perform data cleaning and save the cleaned data to a file done successfully.
