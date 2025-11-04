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
df=pd.read_csv('SAMPLEIDS.csv')
df
```
<img width="617" height="489" alt="image" src="https://github.com/user-attachments/assets/00302dad-06f5-4da7-80ae-0687d42059b2" />

```
df.head()
```
<img width="653" height="150" alt="image" src="https://github.com/user-attachments/assets/0ad1820e-b281-455a-9c99-e65abc724009" />

```
df.tail()
```

<img width="766" height="151" alt="image" src="https://github.com/user-attachments/assets/a5314896-a3b7-4d4b-b91e-3206cbbc6ba1" />

```
df.isnull()
```

<img width="581" height="482" alt="image" src="https://github.com/user-attachments/assets/3f8cf7e7-22df-4fa0-bdca-4f7ce41055b8" />

```
df.notnull()
```

<img width="568" height="483" alt="image" src="https://github.com/user-attachments/assets/e92ecca8-4b04-4ce5-8e0e-c53e6f99d5de" />

```
df.isnull().sum()
```

<img width="256" height="198" alt="image" src="https://github.com/user-attachments/assets/06c7574f-e098-4cd4-a124-ad2312c57ae8" />

```
df.isnull().any()
```

<img width="256" height="197" alt="image" src="https://github.com/user-attachments/assets/e69b4fa2-7000-42e1-b53a-f8a97c6af553" />

```
df.dropna(axis=0)
```

<img width="713" height="316" alt="image" src="https://github.com/user-attachments/assets/7ff7b884-502e-4707-9153-1ec960cd6053" />

```
df.dropna(axis=1)
```

<img width="426" height="479" alt="image" src="https://github.com/user-attachments/assets/0124b147-0561-45da-af87-ba65364c8658" />

```
df.fillna(_)
```

<img width="689" height="486" alt="image" src="https://github.com/user-attachments/assets/38023fa1-c567-41ef-a74a-89f22f4fb186" />

```
df.fillna(method='ffill')
```

<img width="633" height="484" alt="image" src="https://github.com/user-attachments/assets/1bb7a3c1-b628-485e-a444-7304adf118d1" />

```
df.fillna(method='bfill')
```

<img width="720" height="480" alt="image" src="https://github.com/user-attachments/assets/af0c0576-7626-4cb0-919c-f13d6730a41f" />

```
df.fillna({'GENDER':'MALE','NAME':'SANTHOSH','ADDRESS':'KANCHIPURAM','M1':'76.0','M2':'69.0','M3':'80.0','M4':'76.0','TOTAL':'301.0','AVG':'100.333333'})
```

<img width="665" height="484" alt="image" src="https://github.com/user-attachments/assets/1b6898ce-db9f-4c4d-ae51-748ea6329dcd" />

```
import pandas as pd
ir=pd.read_csv("iris.csv")
ir
```

<img width="520" height="300" alt="image" src="https://github.com/user-attachments/assets/e60c63b6-b372-4e06-8ade-22a6d51bbe12" />

```
ir.describe()
```

<img width="417" height="208" alt="image" src="https://github.com/user-attachments/assets/e056e26f-9e97-48b5-a47f-667500a30c1f" />

```
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)
```

<img width="749" height="400" alt="image" src="https://github.com/user-attachments/assets/13da0652-0bc9-4a0e-baf4-fcc9e7647386" />

```
Q1=ir.sepal_width.quantile(0.25)
Q3=ir.sepal_width.quantile(0.75)
IQR=Q3-Q1
print(IQR)
```

<img width="648" height="30" alt="image" src="https://github.com/user-attachments/assets/5290a526-f57d-491b-aad7-1add2b126ef5" />

```
rid=ir[(ir.sepal_width<(Q1-1.5*IQR))|(ir.sepal_width>(Q3+1.5*IQR))]
rid['sepal_width']
```

<img width="509" height="84" alt="image" src="https://github.com/user-attachments/assets/10f7bd2f-a9db-4647-8de9-2c25da197faa" />

```
delid=ir[~((ir.sepal_width<(Q1-1.5*IQR))|(ir.sepal_width>(Q3+1.5*IQR)))]
delid
```

<img width="503" height="299" alt="image" src="https://github.com/user-attachments/assets/0830f300-2570-4a96-b4f2-22085034e95d" />

```
sns.boxplot(x='sepal_width',data=delid)
```

<img width="587" height="393" alt="image" src="https://github.com/user-attachments/assets/e0841a7e-7fb3-4576-a82c-e0e8f062cfdc" />

```
import numpy as np
import scipy.stats as stats
xyz=np.abs(stats.zscore(ir['sepal_width']))
xyz
```

<img width="500" height="184" alt="image" src="https://github.com/user-attachments/assets/778819a3-e383-491c-8524-0b193079ce8e" />

```
ir1=ir[xyz>3]
ir1
```

<img width="552" height="66" alt="image" src="https://github.com/user-attachments/assets/2d7860a5-f553-4e0f-944b-626f51a9f80a" />

# Result

Thus the data cleaning process on the given dataset is executed successfully.
