---
jupyter:
  jupytext:
    formats: ipynb,md
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.1'
      jupytext_version: 1.2.4
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
---

# Steven Luu


**Instructions:** This is an individual assignment, but you may discuss your code with your neighbors.


# Python and NumPy

While other IDEs exist for Python development and for data science related activities, one of the most popular environments is Jupyter Notebooks.

This lab is not intended to teach you everything you will use in this course. Instead, it is designed to give you exposure to some critical components from NumPy that we will rely upon routinely.

## Exercise 0
Please read and reference the following as your progress through this course. 

* [What is the Jupyter Notebook?](https://nbviewer.jupyter.org/github/jupyter/notebook/blob/master/docs/source/examples/Notebook/What%20is%20the%20Jupyter%20Notebook.ipynb#)
* [Notebook Tutorial](https://www.datacamp.com/community/tutorials/tutorial-jupyter-notebook)
* [Notebook Basics](https://nbviewer.jupyter.org/github/jupyter/notebook/blob/master/docs/source/examples/Notebook/Notebook%20Basics.ipynb)

**In the space provided below, what are three things that still remain unclear or need further explanation?**


1. If you write functions in other notebooks, can you call them across different notebooks?

2. I'm still unsure of when you should use numpy dimensions like (1,1) vs (,1)

3. Is there an easy way to create notebook files from md files locally?


## Exercises 1-7
For the following exercises please read the Python appendix in the Marsland textbook and answer problems A.1-A.7 in the space provided below.


## Exercise 1

```python
# YOUR SOLUTION HERE
import numpy as np
a = np.empty((6,4),dtype= np.int)
a.fill(2)
a
```

## Exercise 2

```python
# YOUR SOLUTION HERE

b = np.empty((6,4), dtype = np.int)
b.fill(2)
np.fill_diagonal(b, 3)
b
```

## Exercise 3


**a * b multiplies the numbers that are in the same spot, but**
**np.dot(a,b) uses actual matrix multiplication, and the dimensions** 
**are not compatible to do so**



## Exercise 4

```python
# YOUR SOLUTION HERE
print(np.dot(a.transpose(),b))
# (6 x 4) * (4 * 6)
#      ^_____^

print(np.dot(a,b.transpose()))
# (4 x 6) * (6 x 4)
#      ^_____^



# The results are different shapes because the inside numbers are
# different from the matrix multiplication
```

## Exercise 5

```python
# YOUR SOLUTION HERE
def printThing():
    print("Hello World!")
    
printThing()
```

## Exercise 6

```python
# YOUR SOLUTION HERE

def createArray():
    arr1 = np.random.randint(0, 20, (6, 5))
    
    
    print(arr1)
    print("Mean of Array is: ", arr1.mean())
    print("Sum of Array is: ", arr1.sum())
    
    
createArray()
    
```

## Exercise 7

```python
# YOUR SOLUTION HERE
arr1 = np.random.randint(0, 2, (1, 5, 5))
arr1 = arr1.reshape(5,5)
ones = 0
print(arr1)
for row in arr1:
    for value in row:
        if value == 1:
            ones += 1
print(ones)
arr1[np.where(arr1==1)].sum()
```

## Excercises 8-???
While the Marsland book avoids using another popular package called Pandas, we will use it at times throughout this course. Please read and study [10 minutes to Pandas](https://pandas.pydata.org/pandas-docs/stable/getting_started/10min.html) before proceeding to any of the exercises below.


## Exercise 8
Repeat exercise A.1 from Marsland, but create a Pandas DataFrame instead of a NumPy array.

```python
# YOUR SOLUTION HERE
import pandas as pd
a = pd.DataFrame(np.ones((6,4)) * 2)
a
```

## Exercise 9
Repeat exercise A.2 using a DataFrame instead.

```python
# YOUR SOLUTION HERE
b = np.ones((6,4)) * 2
b = pd.DataFrame(b)
b.iloc[range(4),range(4)] =3
b
```

## Exercise 10
Repeat exercise A.3 using DataFrames instead.

```python
# YOUR SOLUTION HERE

print(a.multiply(b))
#a.dot(b)
```

## Exercise 11
Repeat exercise A.7 using a dataframe.

```python
# YOUR SOLUTION HERE
arr1 = np.random.randint(0, 2, (5, 5))
df = pd.DataFrame(arr1)
print(df)
ones = 0
for i in range(len(df)):
    for num in df[i]:
        if num == 1:
            ones += 1
print(ones)
int(df[df == 1].sum().sum())
```

## Exercises 12-14
Now let's look at a real dataset, and talk about ``.loc``. For this exercise, we will use the popular Titanic dataset from Kaggle. Here is some sample code to read it into a dataframe.

```python
titanic_df = pd.read_csv(
    "https://raw.githubusercontent.com/dlsun/data-science-book/master/data/titanic.csv"
)
titanic_df

```

Notice how we have nice headers and mixed datatypes? That is one of the reasons we might use Pandas. Please refresh your memory by looking at the 10 minutes to Pandas again, but then answer the following.


## Exercise 12
How do you select the ``name`` column without using .iloc?

```python
## YOUR SOLUTION HERE
titanic_df.name
```

## Exercise 13
After setting the index to ``sex``, how do you select all passengers that are ``female``? And how many female passengers are there?

```python
## YOUR SOLUTION HERE
titanic_df.set_index('sex',inplace=True)
females = titanic_df.loc['female']
len(females)
```

## Exercise 14
How do you reset the index?

```python
## YOUR SOLUTION HERE
titanic_df.reset_index(inplace = True)
```

```python

```
