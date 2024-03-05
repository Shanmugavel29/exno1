Exno:1
Data Cleaning Process

AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

Coding and Output
# Developed By: MUKKESH R
# Register Number: 212223240100
1) Read and display DataFrame
import pandas as pd
df=pd.read_csv('/content/SAMPLEDS.csv')
df
OUTPUT:
image

2) Display head
df.head()
OUTPUT:
image

3) Display tail
df.tail()
OUTPUT:
image

4) Info of datafram
df.info()
OUTPUT:
image

5) Describe about the dataframe
df.describe()
OUTPUT:
image

6) Shape of the datafram
df.shape
OUTPUT:
image

7) Checking tha NUll values
df.isnull().sum()
OUTPUT:
image

8) Drop the Null values
x=df.dropna(how='any')
x
OUTPUT:
image

9) Drop the Null values in Total
tot=df.dropna(subset=['TOTAL'],how='any')
tot
OUTPUT:
image

10) FIll the Null values
df.fillna(0)
OUTPUT:
image

11) Finding the mean value
mn=df.TOTAL.mean()
mn
OUTPUT:
image

12) Fill Null value with Mean value
df.head()
OUTPUT:
Screenshot 2024-02-23 090324

13) Final output
for x in df.index:
  if df.loc[x,"AVG"]>100:
    df.drop(x,inplace=True)
df
OUTPUT:
image

14)Cut and paste portion of image
     import cv2
     image=cv2.imread('Deepika.jpg',1)
     image=cv2.resize(image,(400,400))
     tag =image[150:200,110:160]
     image[110:160,150:200] = tag
     cv2.imshow('partimage1',image)
     cv2.waitKey(0)
     cv2.destroyAllWindows()
OUTPUT:
deepikasrinivasanDIPT1

Result
The data clearning has beeen done successfully.
