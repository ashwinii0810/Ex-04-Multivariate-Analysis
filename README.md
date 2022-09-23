                                                              Ex-04-Multivariate-Analysis
AIM:
  To apply multivariate analysis on a give data set.

Algorithm:

 1.start
 
 2.read the dta from the file
 
 3.clean the data
   a)remove outliers
   b)fill the null value or drop the column
   
 4.perform multivariate analysis
   a)scatter plot
   b)box plot
   c)heat map
   
 Program:
   read and cleaned the null value:
   code:
   import pandas as pd
   
df=pd.read_csv("/content/SuperStore.csv")

df['Postal Code']=df['Postal Code'].fillna(df['Postal Code'].mode()[0])

df.isnull().sum()

   ![image](https://user-images.githubusercontent.com/95408674/191993132-dc321a21-f671-4e2f-884a-58fdf7cefd2a.png)
   
  scatter plot:
  
  df.dtypes:
  
  code:
  
  df.dtype
  
  output:
  
  ![image](https://user-images.githubusercontent.com/95408674/191994464-42688b81-002e-4694-960c-513fcd3ccf88.png)
  
  kurtosis:
  
  df.kurtosis()
  
  code:
  
  output:
  
  ![image](https://user-images.githubusercontent.com/95408674/191994769-7fb4db1a-789d-469a-883c-977d8db092af.png)
  
  scatter plot:
  
  code:
  
  import pandas as pd

import seaborn as sns

sns.boxplot(df['Sales'],df['Postal Code'])

output:

![image](https://user-images.githubusercontent.com/95408674/191995583-06e9ab6c-44be-4928-8488-125fd169743e.png)

Bar plot:

code:

sns.barplot(x=df["Sales"],y=df["Postal Code"],data=df)

![image](https://user-images.githubusercontent.com/95408674/191996705-9b6d0169-cf54-4c9a-8935-8671129bf4b1.png)

bar plot

code:

import pandas as pd

import seaborn as sns

import matplotlib.pyplot as plt

states=df.loc[:,["Postal Code","Sales"]]

states=states.groupby(by=["Postal Code"]).sum().sort_values(by="Sales")

plt.figure(figsize=(17,7))

sns.barplot(x=states.index,y="Sales",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("Postal Code")

plt.ylabel=("Sales")

plt.show()

output:

![image](https://user-images.githubusercontent.com/95408674/191998194-3e9c2e04-8841-442b-a2a7-42ce392fbfdd.png)

code:

import pandas as pd

import seaborn as sns
import matplotlib.pyplot as plt

states=df.loc[:,["State","Postal Code"]]

states=states.groupby(by=["State"]).sum().sort_values(by="Postal Code")

plt.figure(figsize=(17,7))

sns.barplot(x=states.index,y="Postal Code",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("Sales")

plt.ylabel=("Postal Code")

plt.show()

corr:

df.corr()

output:
![image](https://user-images.githubusercontent.com/95408674/191999885-7f7284bd-3e7e-4dd2-a85d-38ea33700b9f.png)

  
  ![image](https://user-images.githubusercontent.com/95408674/191998689-7f0ef21b-176a-4c28-9edc-9866f7760317.png)
Heatmap:
code:

import numpy as np

import seaborn as sn

import matplotlib.pyplot as plt

data=pd.read_csv("/content/SuperStore.csv")

data = np.random.randint(low = 1,
						high = 100,
						size = (10, 10))

print("The data to be plotted:\n")

print(data)

hm = sn.heatmap(data = data)

plt.show()

output:
![image](https://user-images.githubusercontent.com/95408674/192001057-49bac8e2-c5a7-4082-a542-ed6e01183c37.png)

RESULT:
  
  Thus we have applied the multiivariate analysis sucessfully






