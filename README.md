## NAME:SUJITHRA K
## REGISTER NUMBER:212223040212
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
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```
```
dt=pd.read_csv("titanic_dataset.csv")
dt
```
![318388789-13922c7c-02df-44cb-ae9e-b4cdaf2aabb1](https://github.com/user-attachments/assets/c378feb9-059e-4b29-99c1-fd887cbead8e)
```
dt.info()
```
![318388774-e8d326dd-02de-4de8-b1de-d719a0585874](https://github.com/user-attachments/assets/31a7c1fa-b602-4c46-bdda-df5e4aa31209)
```
dt.set_index("PassengerId",inplace=True)

dt.set_index("PassengerId",inplace=True)
```
![318388731-378c6da5-d155-41ae-b2d5-8f1bb06079f8](https://github.com/user-attachments/assets/db411330-07a6-4ee0-9f30-033b01f7b7d0)
```
dt.nunique()
```

![318388717-dfbd6c2e-47e1-43f5-adb1-452bc45da9d4](https://github.com/user-attachments/assets/8b40ec57-11a5-450a-8a45-fe7a9fa08d8f)
```
dt["Survived"].value_counts()
```
![318388691-905d2dac-0c87-471f-be7e-5ab44e52ef3e](https://github.com/user-attachments/assets/f89ee579-44be-4b5d-9d05-5af8a84a777c)
```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![318388676-ae6fe782-6c61-47c7-b27a-6c962bedf8d6](https://github.com/user-attachments/assets/447d136f-2c30-4d69-839e-8796c5ebbce6)
```
sns.countplot(data=dt,x="Survived")
```

![318388650-f2914510-5cc0-4769-b3c0-0a4f3532d58b](https://github.com/user-attachments/assets/6198b18f-afca-4f5b-aabb-2ab447960130)
```
dt.Pclass.unique()
```
![318388616-daafb2ad-e26a-4da6-8069-193d54c61b77](https://github.com/user-attachments/assets/5f4f5406-7fc8-45d2-8a1b-65fba7ee8909)
```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![318388587-caf7b020-7cdc-486d-9c21-12c43a0c8ee9](https://github.com/user-attachments/assets/b12750ea-0944-4be5-a52b-98cc6647f9de)
## BIVARIATE ANALYSIS
```
sns.catplot(x="Gender",col="Survived",kind="count", data=dt,height=5,aspect=.7)
```
![318388535-537140a1-50b5-43a6-8d8c-7dcb92ad02fc](https://github.com/user-attachments/assets/7d5eb452-9064-44dd-8ee0-29e27a75aef0)
```
sns.catplot(x="Survived",hue="Gender",data=dt,kind="count"
```

![318388522-98904b6e-6069-4c97-a1ab-a99f94fe564e](https://github.com/user-attachments/assets/3feb0c5d-cedf-494c-a01b-9b986aa1bbce)

```
dt.boxplot(column="Age",by="Survived")
```

![318388506-bac18ead-b349-4c44-a78b-6c7a71fae17b](https://github.com/user-attachments/assets/98dcd084-1762-4b56-82d7-a71937b18630)
```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```

![318388465-5ff46d81-74a0-4bd1-9735-3b16217af504](https://github.com/user-attachments/assets/45b8f8f7-0581-461d-9444-d06929b9347a)
```
sns.jointplot(x=dt["Age"],y=dt["Fare"],data=dt)
```

![318388448-13c887f6-c071-44af-8e7b-f7644a72d7c6](https://github.com/user-attachments/assets/d3391cff-5a66-4e38-b370-32af40b44e3f)

## MULTIVARIATE ANALYSIS
```
fig, ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```

![318388400-065adddf-2696-4d7e-9e4e-ff4515319319](https://github.com/user-attachments/assets/95eabf15-e668-4c0e-a585-bbefe7e6c817)
```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![318388387-477f954b-6f92-48e0-bc1d-3d0feda36c2b](https://github.com/user-attachments/assets/1a304c66-5a70-4811-a3e0-17ad8b9123fb)
```
corr=dt.corr()
sns.heatmap(corr,annot=True)
```

![318388329-50224e99-a7b5-40d6-8dc8-854c1dce2b79](https://github.com/user-attachments/assets/65be88cc-6bc8-4d29-9cfd-bce6166c4ccb)
```
sns.pairplot(dt)
```

![318388299-9e87aaf2-b513-492a-80f3-dc34716b6c9d](https://github.com/user-attachments/assets/6dfc2b70-5988-4baf-b076-fdb598489b96)

# RESULT
        Thus the  Exploratory Data Analysis on the given data set is successfully verified.   
