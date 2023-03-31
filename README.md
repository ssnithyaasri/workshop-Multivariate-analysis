### workshop-Multivariate-analysis

## Aim:

To Perform Bivariate/Multivariate Analysis

## Algorithm:

Read the given data 2.Get information from the data 3.Perform the Bivariate/Multivariate Analysis
Save the clean data to File

## Code:

NAME:Nithyaa sri S S

REG.NO:212222230100

```

import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
df = pd.read_csv("FlightInformation.csv")
df
df.head()
df.info()
df.isnull().sum()
df['Route'] = df['Route'].fillna(df['Route'].mode()[0])
df['Total_Stops'] = df['Total_Stops'].fillna(df['Total_Stops'].mode()[0])
df.isnull().sum()
df.shape
plt.figure(figsize=(8,5))
plt.xticks(rotation = 80)
sns.barplot(df["Airline"],df["Price"],hue=df["Total_Stops"])
states=df.loc[:,["Source","Price"]]
states=states.groupby(by=["Source"]).sum().sort_values(by="Price")
plt.figure(figsize=(8,7))
sns.barplot(x=states.index,y="Price",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SOURCE")
plt.ylabel=("PRICE")
plt.show()
plt.figure(figsize=(5,7))
sns.scatterplot(df['Source'], df['Price'], hue=df['Destination'])
plt.xticks(rotation = 90)
df_count = df.groupby(by=["Source"]).count()
labels=[]
for i in df_count.index:
    labels.append(i)
plt.figure(figsize=(8,8))
colors = sns.color_palette("Set2")
plt.pie(df_count["Price"], colors = colors, labels=labels, autopct = "%0.0f%%",shadow = True) 
plt.title("Source")
plt.show()
df['Airline'].value_counts()
df['Duration'].value_counts()
df_segment = df.groupby(by=["Total_Stops"]).count()
labels = []
for i in df_segment.index:
    labels.append(i)

plt.figure(figsize=(6,6))
colors = sns.color_palette('pastel')
pie = plt.pie(df_segment["Price"], colors = colors, autopct = "%0.0f%%",shadow = True)
plt.title("Total Stops")
plt.legend(pie[0], labels, loc="upper right")
plt.show()
df_region = df.groupby(by=["Destination"]).count()
labels = []
for i in df_region.index:
    labels.append(i)
    
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
pie = plt.pie(df_region["Price"], colors = colors, autopct = "%0.0f%%",shadow = True)
plt.title("Destination")
plt.legend(pie[0], labels, loc="upper right")
plt.show()

```
##output:
![multi 1](https://user-images.githubusercontent.com/119122478/229035398-0254107f-23b6-4051-9ab5-1a3dd1b05ae2.png)
![image](https://user-images.githubusercontent.com/119122478/229035725-0e7f711f-8e18-4d3b-a891-af463a18d2c7.png)
![image](https://user-images.githubusercontent.com/119122478/229035957-3c8bef45-ae41-4b0e-b867-7efdd6abc134.png)
![image](https://user-images.githubusercontent.com/119122478/229036061-990dce2f-708b-41be-8b67-701bf8dfe16d.png)
![image](https://user-images.githubusercontent.com/119122478/229036144-15b91461-5fda-421d-899e-73cc5b6dda9b.png)
![image](https://user-images.githubusercontent.com/119122478/229036264-0d35f849-67a0-482d-a0bd-ce41ee93afc5.png)
![image](https://user-images.githubusercontent.com/119122478/229036598-0781b0dc-2305-4a66-af8d-637172a55ef9.png)
![image](https://user-images.githubusercontent.com/119122478/229036771-9f63684b-e4ab-44e8-a50f-630db426c012.png)
![image](https://user-images.githubusercontent.com/119122478/229037010-84d15353-2ec8-4119-8297-6783e9a4e8be.png)
![image](https://user-images.githubusercontent.com/119122478/229037179-9d4199fe-0a55-4dcb-9637-da5910dcbdb5.png)
![image](https://user-images.githubusercontent.com/119122478/229037380-78731fb6-054a-4f07-aef0-a776d1af1db6.png)

![image](https://user-images.githubusercontent.com/119122478/229037601-eda6cc46-e09b-47c2-9d43-4bcf39c87a59.png)

![image](https://user-images.githubusercontent.com/119122478/229037763-edca0e13-8441-44e4-8537-1a1136376581.png)
![image](https://user-images.githubusercontent.com/119122478/229037919-58f43a95-4516-4774-b38f-3ca7d724960e.png)
![image](https://user-images.githubusercontent.com/119122478/229038041-c67c0345-e77f-4c99-b634-2e5d5d810164.png)

## Result :

Thus we applied Bivariate/Multivariate Analysis Successfully







