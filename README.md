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

# Coding and Output :
Data cleaning process:
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df   

![1](https://github.com/user-attachments/assets/23866177-0ef4-41c1-8a41-ef21ac736ef5)

df.head()

![2](https://github.com/user-attachments/assets/686b55c9-e322-4c47-8828-f5121a041864)

df.tail(5)

![3](https://github.com/user-attachments/assets/ffb1454a-d5ae-4222-a0d0-837bcbc49f2d)

df.isnull()

![4](https://github.com/user-attachments/assets/32005858-81e9-451f-a049-90847193afb3)

df.notnull()

![6](https://github.com/user-attachments/assets/7fcebb06-f623-4031-aa66-e398a0bd9338)

df.dropna(axis=0)

![7](https://github.com/user-attachments/assets/616a31a8-c059-4cdf-8885-c1d0801aefcf)

df.dropna(axis=1)

![8](https://github.com/user-attachments/assets/b7a9b0dd-d527-404f-80e6-48495223bd74)

df.fillna(0)

![9](https://github.com/user-attachments/assets/2e3c12bb-da80-4aa8-96e0-ac61156c7ece)

print(df.shape)

![363191408-bef54714-c7f9-48a6-89f7-71feb365d436](https://github.com/user-attachments/assets/d1c1c355-b656-4680-9341-67c23ba51151)

IQR:
import pandas as pd
import seaborn as sns
ir=pd.read_csv('/content/iris.csv')
ir

![10](https://github.com/user-attachments/assets/15ef0da0-137c-420e-addc-9cef947111d5)

ir.describe()

![11](https://github.com/user-attachments/assets/e4861f26-16bd-4525-9923-cd594176eaf6)

sns.boxplot(x='sepal_width',data=ir)

![12](https://github.com/user-attachments/assets/f996363a-897e-43b7-ae77-ab27f80b276c)

c1=ir.sepal_width.quantile(0.25)
c3=ir.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)

![13](https://github.com/user-attachments/assets/9ebde3c7-ebde-41c3-8db1-ba9aacf442b7)

rid=ir[((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']

![14](https://github.com/user-attachments/assets/6d73d3a8-4b99-41a9-b00d-e3d9a0a9d337)

delid=ir[~((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
delid
sns.boxplot(x='sepal_width',data=delid)

![17](https://github.com/user-attachments/assets/04238c84-3dc8-42b7-a3da-42bcb57c441b)

import matplotlib.pyplot as plt
import pandas as pd
import pandas as pd
import numpy as np
import scipy.stats as stats
dataset=pd.read_csv("/content/heights.csv")
dataset

![18](https://github.com/user-attachments/assets/4872b1b2-1e5e-49ce-81c6-85f645fb0871)

df = pd.read_csv("heights.csv")
q1 = df['height'].quantile(0.25)
q2 = df['height'].quantile(0.5)
q3 = df['height'].quantile(0.75)
iqr = q3-q1
iqr

![19](https://github.com/user-attachments/assets/f9a1775c-bb68-48ac-927b-d4229c43f301)

low = q1 - 1.5*iqr
low

![20](https://github.com/user-attachments/assets/4b15925c-1425-4166-a698-f5444b91eb55)

high = q3 + 1.5*iqr
high

![363193753-d9389aa7-e169-42df-aed4-037dd72cb08d](https://github.com/user-attachments/assets/6669fe41-3a49-465a-bc42-12aa7b193bbf)

df1 = df[((df['height'] >=low)& (df['height'] <=high))]
df1

![21](https://github.com/user-attachments/assets/7ebb63e6-c9a2-470b-90ab-5805992ad85b)

z = np.abs(stats.zscore(df['height']))
z

![22](https://github.com/user-attachments/assets/2ce75404-7c5e-4b7a-8031-3bd168414716)

 df1 = df[z<3]
 df1
 
![23](https://github.com/user-attachments/assets/2f733ced-9195-410e-bf9e-4b3a710e0bff)

# Result :
      Thus the Data Cleaning Process and Detecting and Removal of Outliers is executed successfully.  
