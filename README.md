# Ex02-Outlier

You are given bhp.csv which contains property prices in the city of banglore, India. You need to examine price_per_sqft column and do following,

(1) Remove outliers using IQR 

(2) After removing outliers in step 1, you get a new dataframe.

(3) use zscore of 3 to remove outliers. This is quite similar to IQR and you will get exact same result

(4) for the data set height_weight.csv find the following

    (i) Using IQR detect weight outliers and print them

    (ii) Using IQR, detect height outliers and print them 

## AIM:
TO detect and remove the outliers in the given data set and save the final data.

## Algorithm:
## Step 1
Import the required packages(pandas,numpy,scipy)

## Step 2
Read the given csv file use read_csv()

## Step 3
Convert the file into a dataframe and get information of the data.

## Step 4
Remove the non numerical data columns using drop() method.

## Step 5
Detect the outliers in the data set using z scores method.

## Step 6
Remove the outliers by z scores and list manupilation or by using Interquartile Range(IQR)

## Step 7
Check if the outliersare removed from data set using graphical methods.

## Step 8
Save the final data set into the file.

# Program:
### (i)For the data set height_weight.csv detect weight outliers using IQR method
```python
import pandas as pd
import numpy as np
import seaborn as sns
from scipy import stats
df=pd.read_csv("/content/height_weight.csv")
df
sns.boxplot(x="weight",data=df)
q1 = df["weight"].quantile(0.25)
q3 = df['weight'].quantile(0.75)
print("First Quantile = ",q1,"\nSecond Quantile = ",q3)
IQR = q3-q1
low = q1-1.5*IQR
high = q3+1.5*IQR
df4 =df[((df['weight']>=low)&(df['weight']<=high))]
df4
sns.boxplot(x="weight",data=df4)
```
### (ii) For the data set height_weight.csv detect height outliers using IQR method.
```python 
sns.boxplot(x="height",data=df)
q1 = df["height"].quantile(0.25)
q3 = df['height'].quantile(0.75)
print("First Quantile = ",q1,"\nSecond Quantile = ",q3)
IQR = q3-q1
low = q1-1.5*IQR
high = q3+1.5*IQR
df4 =df[((df['height']>=low)&(df['height']<=high))]
df4
sns.boxplot(x="height",data=df4)
sns.scatterplot(data=df4)
sns.boxplot(data=df4)
```
# Output
![output](o1.png)
![output](o2.png)
![output](o3.png)
![output](o4.png)
![output](o5.png)
![output](o6.png)
![output](o7.png)