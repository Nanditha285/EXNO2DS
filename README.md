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
        <<INCLUDE YOUR CODING AND OUTPUT SCREENSHOTS>>

# RESULT
        <<INCLUDE YOUR RESULT HERE>>



import pandas as pd

df=pd.read_csv(r"C:\Users\acer\Downloads\titanic_dataset.csv")

df

<img width="1403" height="498" alt="image" src="https://github.com/user-attachments/assets/e8949cc3-d6e0-4ac3-8c99-cff13edfff0c" />


df.shape

<img width="1503" height="37" alt="image" src="https://github.com/user-attachments/assets/eee1a32d-bebe-4016-a146-48fd6acafdbd" />


df.set_index("PassengerId",inplace=True)
df

<img width="1492" height="522" alt="image" src="https://github.com/user-attachments/assets/c308512d-f74b-44f3-8dd4-a57e94548013" />


df.nunique()

<img width="563" height="300" alt="image" src="https://github.com/user-attachments/assets/ee4f4602-3997-4c3a-bc66-f478d070a873" />


df['Sex'].value_counts()

<img width="386" height="97" alt="image" src="https://github.com/user-attachments/assets/49e98850-ce9c-4f57-88cd-e5f039cb790d" />


df.Survived.unique()

<img width="1504" height="52" alt="image" src="https://github.com/user-attachments/assets/5723009d-5a9e-4ae6-bac0-7609a5681735" />


df.rename(columns={"Sex":"Gender"},inplace=True)

df

<img width="1451" height="536" alt="image" src="https://github.com/user-attachments/assets/d126ff23-dffe-4356-b76f-dea65c9d41c2" />


import seaborn as sns

sns.countplot(data=df)


<img width="989" height="625" alt="image" src="https://github.com/user-attachments/assets/72e83b9d-7344-48a0-9470-4c9822a1a6ff" />


sns.countplot(x="Survived",hue="Gender",data=df)

<img width="993" height="635" alt="image" src="https://github.com/user-attachments/assets/e00f9740-fe15-4413-8e1c-88b7610c3bcc" />


sns.catplot(x="Survived",hue="Gender",data=df,kind="count")

<img width="980" height="722" alt="image" src="https://github.com/user-attachments/assets/906f4bca-b1b4-424e-9f9a-b7bf4be97ebc" />


sns.catplot(x="Survived",hue="Gender",data=df,kind="violin")

![WhatsApp Image 2025-10-07 at 16 06 10_83acbaa3](https://github.com/user-attachments/assets/4bd7ed53-72b4-4d47-86dd-ace90fba7ae0)


sns.boxplot(data=df)

<img width="798" height="617" alt="image" src="https://github.com/user-attachments/assets/eb46e75e-a603-4ead-ae2e-9c568f0653ab" />


sns.scatterplot(data=df)

<img width="829" height="638" alt="image" src="https://github.com/user-attachments/assets/9385baf0-8b69-4d35-909c-0819d4c5ad87" />


sns.scatterplot(x=df['Age'],y=df['Fare'])

<img width="886" height="618" alt="Screenshot 2025-10-07 214720" src="https://github.com/user-attachments/assets/a7b62f38-be72-4d2e-aa7b-84bcab3c120f" />


sns.jointplot(x='Age',y='Fare',data=df)

<img width="724" height="699" alt="image" src="https://github.com/user-attachments/assets/66bcc2cd-c480-4b8a-8a72-061640b12cc9" />


sns.jointplot(x='Age',y='Fare',data=df,kind='kde')

<img width="678" height="696" alt="Screenshot 2025-10-07 215252" src="https://github.com/user-attachments/assets/1a6f02c4-63e2-4807-bc51-9f62c62dc0cc" />


sns.jointplot(x='Age',y='Fare',data=df,kind="hist")

<img width="678" height="696" alt="Screenshot 2025-10-07 215252" src="https://github.com/user-attachments/assets/9f15fc59-64d6-48bc-ba72-58e1a6b963e7" />


sns.pairplot(data=df)

<img width="622" height="642" alt="Screenshot 2025-10-07 221143" src="https://github.com/user-attachments/assets/b33412e3-7d47-49cc-b68e-7143de64c3cc" />


corr1=df.select_dtypes(include=["number"]).corr()

sns.heatmap(corr1,annot=True)

<img width="598" height="476" alt="Screenshot 2025-10-07 220446" src="https://github.com/user-attachments/assets/c0234f17-cd10-460f-aeda-eac071aec6eb" />


sns.catplot(x='Gender',col='Survived',data=df,kind='count',color='green')

![WhatsApp Image 2025-10-07 at 16 06 10_68f7b666](https://github.com/user-attachments/assets/88956ccf-c8c3-4af1-b6ee-53f2d620615d)


df.boxplot(column="Survived",by="Gender")

![WhatsApp Image 2025-10-07 at 16 06 10_68f7b666](https://github.com/user-attachments/assets/f7fb2c8a-90ac-49cd-bf2c-bbae69a658a7)


sns.catplot(data=df,col="Suvived",x="Gender",hue="Pclass",kind="count")



























