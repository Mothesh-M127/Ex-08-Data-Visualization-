# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE:
```
Developed by:Mothesh.M
Reg No:212221230066
```
```
import pandas as pd
df=pd.read_csv("Superstore.csv")
df

df.isnull()

df.isnull().sum()

#Data Visualization using Seaborn
import seaborn as sns
from matplotlib import pyplot as plt

plt.figure(figsize=(9,6))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)

sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)

sns.lineplot(x="Category",y="Sales",data=df,marker='o')

sns.scatterplot(x='Category',y='Sub-Category',data=df)

sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)

plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)

sns.boxplot(x="Sub-Category",y="Discount",data=df)

sns.boxplot( x="Profit", y="Category",data=df)

sns.violinplot(x="Profit",data=df)

sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)

sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)

sns.pointplot(x=df["Quantity"],y=df["Discount"])

sns.countplot(x="Category",data=df)

sns.countplot(x="Sub-Category",data=df)

sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')

sns.kdeplot(x="Profit", data = df,hue='Category')

#Data Visualization Using MatPlotlib
plt.plot(df['Category'], df['Sales'])
plt.show()

df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)

df1=df.groupby(by=["Ship Mode"]).sum()
labels=[]
for i in df1.index:
    labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()

df3=df.groupby(by=["Category"]).sum()
labels=[]
for i in df3.index:
    labels.append(i) 
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df3["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()

plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()

plt.bar(df.index,df['Category'])
plt.show()

plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show() 

plt.boxplot(x="Sales",data=df)
plt.show()
```

# OUPUT:
![ot1](https://user-images.githubusercontent.com/94170892/172288382-daea6c47-8451-4ff1-ad89-347c2a81403f.jpg)
![ot2](https://user-images.githubusercontent.com/94170892/172288415-cc6bb869-4ea4-4ea1-8de4-3694c7384c24.jpg)

## Data Visualization By Seaborn
### Line Plot:
![ot3](https://user-images.githubusercontent.com/94170892/172288440-0e3359ef-9f5b-40a7-b82d-94fb1f8e3d85.jpg)
![ot4](https://user-images.githubusercontent.com/94170892/172288500-a11295ea-2639-4da2-b7fd-b1c705e11bc5.jpg)
![ot5](https://user-images.githubusercontent.com/94170892/172288532-3583a5da-6c67-4733-8d4e-a5b7bf312f04.jpg)

### Scatter Plot:
![ot6](https://user-images.githubusercontent.com/94170892/172288580-d520458b-ecc9-4926-b92c-713786a5c71d.jpg)
![ot7](https://user-images.githubusercontent.com/94170892/172288630-ab35e1ea-8ced-42e7-9c16-f1a677fb7d80.jpg)
![ot8](https://user-images.githubusercontent.com/94170892/172288641-032f647a-e960-4ec8-9f4d-955cf7b8c531.jpg)

### Box Plot:
![ot9](https://user-images.githubusercontent.com/94170892/172288697-05a97be4-d3bb-495b-968c-defe86e6388c.jpg)
![ot10](https://user-images.githubusercontent.com/94170892/172288711-618f6d95-f7aa-4fb4-aae7-af50bf2d29fe.jpg)

### Violin Plot:
![ot11](https://user-images.githubusercontent.com/94170892/172288754-ac42497d-17d6-455e-b5b8-d7ddb5291368.jpg)

### Barplot:
![ot12](https://user-images.githubusercontent.com/94170892/172288797-7b6538f3-803a-4ec5-917a-af3e8ae294aa.jpg)
![ot13](https://user-images.githubusercontent.com/94170892/172288815-d5490f7a-55f4-4d22-946b-b8fcefff0ae0.jpg)

### Pointplot:
![ot14](https://user-images.githubusercontent.com/94170892/172288883-a8f1b3a3-0fb6-4124-b368-e05af9c84eae.jpg)

### Countplot:
![ot15](https://user-images.githubusercontent.com/94170892/172288916-acf18e63-56ea-47eb-82a5-9b14c71377ca.jpg)
![ot16](https://user-images.githubusercontent.com/94170892/172288951-eb22343b-d5bc-4cf7-9f8b-678417459f5a.jpg)

### Histogram:
![ot17](https://user-images.githubusercontent.com/94170892/172288987-ede47b4e-912a-4b12-81c5-5478933740c0.jpg)

### KDE Plot:
![ot18](https://user-images.githubusercontent.com/94170892/172289024-e504df91-65dc-4f2b-87e5-b01ae69744ba.jpg)

## Data Visualization By Matplotlib:
### Plot:
![ot19](https://user-images.githubusercontent.com/94170892/172289095-11eb25cc-afa3-4b97-b14a-d9343f4b4b77.jpg)

### Heatmap:
![ot20](https://user-images.githubusercontent.com/94170892/172289132-f7888d93-6836-438d-829b-aeff02a6d54b.jpg)

### Piechart:
![ot21](https://user-images.githubusercontent.com/94170892/172289164-296dbbef-810f-4cd6-b45d-328ff4324517.jpg)
![ot22](https://user-images.githubusercontent.com/94170892/172289171-0b83d459-e98d-4464-a494-33425351267f.jpg)

### Histogram:
![ot23](https://user-images.githubusercontent.com/94170892/172289207-3c229377-679d-404b-9fb6-34c56c98129d.jpg)

### Bargraph:
![ot24](https://user-images.githubusercontent.com/94170892/172289235-05ea5dd8-b32f-40c7-a653-3a2236012d8d.jpg)

### Scatterplot:
![ot25](https://user-images.githubusercontent.com/94170892/172289266-2c4dc556-b86d-43d5-a12d-60e3e7d943ad.jpg)

### Boxplot:
![ot26](https://user-images.githubusercontent.com/94170892/172289314-492142d1-44be-4e85-8bc5-c4dcf205f1cf.jpg)

## RESULT:
Thus Data Visualization is applied on the given dataset using libraries like Seaborn and Matplotlib successfully.
