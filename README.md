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
import pandas as pd df=pd.read_csv("/content/SAMPLEIDS.csv") df
![s 1](https://github.com/Iswarya0580/exno1/assets/149989171/5f298ee2-b6c5-4080-aacb-0ebea0781415)

df.head()

![s2](https://github.com/Iswarya0580/exno1/assets/149989171/03f344f7-a60b-46ee-9123-f9d939a80101)

df.tail()

![s3](https://github.com/Iswarya0580/exno1/assets/149989171/5f67e7b3-73dd-4485-b202-94ce6a37c8f1)

df.describe()

![s4](https://github.com/Iswarya0580/exno1/assets/149989171/e567620b-9a95-4505-9401-f96388621e96)

df.info()

![s5](https://github.com/Iswarya0580/exno1/assets/149989171/11538302-c77e-4af3-9193-3b029ad300df)

df.shape

![s6](https://github.com/Iswarya0580/exno1/assets/149989171/ab79d662-2ab0-4da1-bd4b-bd70d5511588)

df.isnull().sum()

![s7](https://github.com/Iswarya0580/exno1/assets/149989171/5ac8cfee-4bc6-4db9-8724-923544f024b6)


df.nunique()

![s8](https://github.com/Iswarya0580/exno1/assets/149989171/04b99ce6-d21a-4e81-8d1d-866284f17b73)


mn=df.TOTAL.mean()
mn

![s9](https://github.com/Iswarya0580/exno1/assets/149989171/fbf4fc71-a00b-4f01-89cc-a66e8922423e)


df.TOTAL.fillna(mn,inplace=True)
df

![s10](https://github.com/Iswarya0580/exno1/assets/149989171/1c554905-72bd-4687-81f1-fcc94834a95f)


a=df.M4.min()
a

![s11](https://github.com/Iswarya0580/exno1/assets/149989171/6b04f69b-546a-4cc6-9e5f-581b47526927)

df.M4.fillna(a,inplace=True)
df

![image](https://github.com/Iswarya0580/exno1/assets/149989171/968bb8cc-cdd1-4b78-b0da-fb3fe3b03649)

import pandas as pd
import seaborn as sns
import numpy as np

age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af

![s13](https://github.com/Iswarya0580/exno1/assets/149989171/c16dab5c-f192-443c-8d2c-132d7630a1c4)

sns.boxplot(data=af)

![image](https://github.com/Iswarya0580/exno1/assets/149989171/5045e3b4-fd20-44bd-83ee-694bb98fb77a)

q1=af.quantile(0.25)
q2=af.quantile(0.5)
q3=af.quantile(0.75)
iqr=q3-q1
iqr

![image](https://github.com/Iswarya0580/exno1/assets/149989171/323a15f4-e669-4341-a034-4c3cad916a23)

Q1=np.percentile(af,25)
Q3=np.percentile(af,75)
IQR=Q3-Q1
IQR

![image](https://github.com/Iswarya0580/exno1/assets/149989171/6a42ea45-4398-4801-9f55-19f136c702fb)

lower_bound=Q1-1.5*IQR
upper_bound=Q3+1*5*IQR
outliers=[x for x in age if x<lower_bound or x>upper_bound]
print("Q1:",Q1)
print("Q3:",Q3)
print("IQR:",IQR)
print("lower")

![image](https://github.com/Iswarya0580/exno1/assets/149989171/04ac49b9-953a-47dc-992b-ed0e6b01d627)

af=af[((af>=lower_bound)&(af<=upper_bound))]
af

![image](https://github.com/Iswarya0580/exno1/assets/149989171/16ab7a25-0926-43af-831d-482c59d1277a)

af.dropna()

![image](https://github.com/Iswarya0580/exno1/assets/149989171/b0e45b1c-b577-4f86-b3f7-9333e4591f5d)

sns.boxplot(data=af)

![image](https://github.com/Iswarya0580/exno1/assets/149989171/0c9957c4-a176-42dd-b88d-968623038d2c)

data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,102,105]
df=pd.DataFrame(data) 
df

![image](https://github.com/Iswarya0580/exno1/assets/149989171/91f9d5b9-518e-4b14-9710-87f03e699131)

import numpy as np 
from scipy import stats
z=np.abs(stats.zscore(df)) 
z

![s22](https://github.com/Iswarya0580/exno1/assets/149989171/eb28f29d-f806-4080-9a01-6e086d65f137)



# Result
Thus the given program executed successfully.
