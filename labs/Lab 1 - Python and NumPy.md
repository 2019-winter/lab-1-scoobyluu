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


**YOUR ANSWER HERE**


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

def createArrays():
    arr1 = np.random.randint(0, 100, (3, 6, 5))
    arr2 = np.random.randint(0, 100, (3, 6, 5))
    
    print(arr1 + arr2)
    
    
createArrays()
    
```

## Exercise 7

```python
# YOUR SOLUTION HERE

```

## Excercises 8-???
While the Marsland book avoids using another popular package called Pandas, we will use it at times throughout this course. Please read and study [10 minutes to Pandas](https://pandas.pydata.org/pandas-docs/stable/getting_started/10min.html) before proceeding to any of the exercises below.


## Exercise 8
Repeat exercise A.1 from Marsland, but create a Pandas DataFrame instead of a NumPy array.

```python
# YOUR SOLUTION HERE
```

## Exercise 9
Repeat exercise A.2 using a DataFrame instead.

```python
# YOUR SOLUTION HERE
```

## Exercise 10
Repeat exercise A.3 using DataFrames instead.

```python
# YOUR SOLUTION HERE
```

## Exercise 11
Repeat exercise A.7 using a dataframe.

```python
# YOUR SOLUTION HERE
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
```

## Exercise 13
After setting the index to ``sex``, how do you select all passengers that are ``female``? And how many female passengers are there?

```python
## YOUR SOLUTION HERE
titanic_df.set_index('sex',inplace=True)
```

## Exercise 14
How do you reset the index?

```python
## YOUR SOLUTION HERE
```

```python

```
