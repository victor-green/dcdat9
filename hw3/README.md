**General Assembly Dat9 Homework Number 3**

**Linear Algebraic Notation for Data Science**

A dataset can be described as such. A single row is known as a sample, instance or an observation. Each column of data contains attributes which describe the datasets features, measurements, or dimensions. Each row also contains a class label or target identifying data of this type. Given the iris dataset the following is how we'd describe it using these terms.

 1. Number of samples: 150
 2. Number of Dimensions: 4 (Sepal Length, Sepal Width, Pedal length, Pedal Width)
 3. Class labels: 3 (Setosa, Versicolor, Virginica)

| Sepal length | Sepal width | Pedal length  | Pedal width | Class name |
| ----- | ----- | ----- | ----- | ---------- |
| 5.1   | 3.5   | 1.4   | 0.2   | Setosa     |
| 4.9   | 3.0   | 1.4   | 0.2   | Versicolor |
| 6.4   | 3.0   | 4.5   | 1.2   | Virginica  |


We can express these terms in Linear Algebra as such
150 samples , 4 features = 150x4 matrix
1 sample, 4 features = 1x4 vector
1 feature 150 rows = 150x1 vector
3 class labels = 1 vector

We can visualize this dataset in python like so:

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as pl

#Load Iris Dataset
df = pd.read_csv('data/iris.data', header=None)
#print df.tail()

#Select Class Labels
y = df.iloc[0:100, 4].values

#Assign a numeric value to Class
y = np.where(y == 'Iris-setosa', -1, 1)

#Select features
X = df.iloc[0:100, [0, 2]].values

#Visualize Dataset to find something interesting
plt.scatter(X[:50, 0], X[:50, 1],color='red', marker='o', label='setosa')
plt.scatter(X[50:100, 0], X[50:100, 1],color='blue', marker='x', label='versicolor')
plt.xlabel('petal length')
plt.ylabel('sepal length')
plt.legend(loc='upper left')
plt.show()
```

What we see is that the two classes we have initially selected for our analysis are
linearly separable meaning we can draw a straight line through these two classes
on our graph. This allows us to use a number classification algorithms for automatically classifying future data from these classes once we have a trained model. 

Victor Green
