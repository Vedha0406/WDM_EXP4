### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 
### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Program:
## Program 1:
```
import pandas as pd
df=pd.read_csv("C:\\Users\\admin\\Downloads\\clustervisitor.csv")
df
cluster={"Young":(df['Age']<=30),"Middle":(df['Age']<50),"Old":(df['Age']>50)}
count=[]
for g,c in cluster.items():
    visitors=df[c]
    count.append(len(visitors))
    print(f"Visitors in {g} group")
    print(visitors)
    print(count)

```
### Visualization:
```
import matplotlib.pyplot as plt

plt.figure(figsize=(8,6))
plt.bar(cluster.keys(), count, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()
```
## Program 2:
```
from sklearn.preprocessing import StandardScaler
from sklearn.cluster import KMeans
df=pd.read_csv("C:\\Users\\admin\\Downloads\\clustervisitor (Salary).csv")
df
from sklearn.preprocessing import StandardScaler
import pandas as pd

sc = StandardScaler()


df1 = df[['Age']]      
df2 = df[['Salary']]    
df3 = pd.concat([df1, df2], axis=1)

newdf = sc.fit_transform(df3)

print(newdf)

newdf=sc.fit_transform(df[['Age','Salary']])
newdf
kmeans=KMeans(n_clusters=3,random_state=42)
df3['cluster']=kmeans.fit_predict(newdf)
df3
```
### Visualization:
```
plt.scatter(df3['Age'], df3['Salary'], c=df3['cluster'])
plt.xlabel('Age')
plt.ylabel('Income in thousands')
plt.show()
```
### Output:
## Program 1:
<img width="349" height="830" alt="image" src="https://github.com/user-attachments/assets/199fe928-5ea7-4c96-9d55-c2c97d0574ad" />
<img width="349" height="830" alt="image" src="https://github.com/user-attachments/assets/8555c1e5-6fd0-4829-9620-9d72a08c2045" />
## Program 2:
<img width="859" height="740" alt="image" src="https://github.com/user-attachments/assets/ae1da22a-a7c8-431f-9121-e5747a41128b" />
### Result:
The implement Cluster and Visitor Segmentation for Navigation patterns in Python is execute successfully.

