# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
Developed by: A.NABITHRA
Register no: 212224230172
```

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df
```

<img width="1119" height="413" alt="image" src="https://github.com/user-attachments/assets/eca92532-1d07-493e-a3e1-fb24f24543ad" />

```
df.info()
```

<img width="371" height="333" alt="image" src="https://github.com/user-attachments/assets/b6ed2ea1-8b6d-4aaf-841c-3b85b8ee61d0" />

```
df.shape
```
<img width="444" height="33" alt="image" src="https://github.com/user-attachments/assets/56df2222-6d50-41ee-b01f-88c33f421487" />

```
df.set_index("PassengerId",inplace=True)
df.describe()
```

<img width="567" height="284" alt="image" src="https://github.com/user-attachments/assets/d2afdd38-2de7-4019-8f19-1e502abc9d9a" />

```
df.shape
```

<img width="599" height="43" alt="image" src="https://github.com/user-attachments/assets/b6da3a67-13e7-407e-bdfe-c089020be0fe" />

```
df.nunique()
```

<img width="162" height="221" alt="image" src="https://github.com/user-attachments/assets/da63df69-4f49-4775-b36e-7bf446ccca70" />

```
df["Survived"].value_counts()
```

<img width="601" height="63" alt="image" src="https://github.com/user-attachments/assets/694aec7d-8451-44f6-bbcb-f33d1c42ea3a" />

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```

<img width="325" height="70" alt="image" src="https://github.com/user-attachments/assets/0f915916-c95d-4be1-9cdb-28c8c23c078d" />

```
sns.countplot(data=df,x="Survived")
```

<img width="671" height="472" alt="image" src="https://github.com/user-attachments/assets/9e1c3abb-a178-407d-8674-a1295b73d446" />

```
df
```

<img width="1072" height="450" alt="image" src="https://github.com/user-attachments/assets/6bfb80b2-7b91-4c2b-b818-2449f670a3bf" />

```
df.Pclass.unique()
```

<img width="299" height="43" alt="image" src="https://github.com/user-attachments/assets/dc6602df-4fe2-465b-9881-536b74c37dca" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

<img width="1078" height="448" alt="image" src="https://github.com/user-attachments/assets/25179b66-b670-4fb1-a958-1f186a632d0d" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```

<img width="761" height="543" alt="image" src="https://github.com/user-attachments/assets/2c8da2a1-0fa5-4ad7-910c-280b692dea2a" />

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```

<img width="637" height="523" alt="image" src="https://github.com/user-attachments/assets/606defd8-d7c3-43c9-b727-dd9f3d8caf8e" />

```
df.boxplot(column="Age",by="Survived")
```

<img width="638" height="498" alt="image" src="https://github.com/user-attachments/assets/0b623325-f3a7-4ee6-aa7b-a2fae7a55a71" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

<img width="639" height="460" alt="image" src="https://github.com/user-attachments/assets/59434452-7313-452d-aed9-910baa431b67" />
```
sns.jointplot(x="Age",y="Fare",data=df)
```

<img width="651" height="620" alt="image" src="https://github.com/user-attachments/assets/8be97dd3-a420-46d7-bd51-0462ace6473d" />

```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```

<img width="807" height="455" alt="image" src="https://github.com/user-attachments/assets/e326340c-52cc-4d8b-b06d-e4cdd29a618b" />
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

<img width="1091" height="520" alt="image" src="https://github.com/user-attachments/assets/fcbeb5ef-c1bc-4bbf-8e1b-9e543d73b457" />

```
corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)
```

<img width="553" height="460" alt="image" src="https://github.com/user-attachments/assets/18c47205-9671-42c6-9a2a-9df0ba8b68a5" />

```
sns.pairplot(df)
```

<img width="816" height="776" alt="image" src="https://github.com/user-attachments/assets/3722a147-4996-48ec-9d04-8a2c1363ad2a" />

# RESULT
        We have performed Exploratory Data Analysis on the given data set successfully.
