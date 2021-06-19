#  JupyterLab
## Overview

JupyterLab is a next-generation web-based user interface for Project Jupyter.

![0](https://jupyterlab.readthedocs.io/en/stable/_images/interface_jupyterlab.png)

JupyterLab enables you to work with documents and activities such as Jupyter notebooks, text editors, terminals, and custom components in a flexible, integrated, and extensible manner. For a demonstration of JupyterLab and its features,.


## Three components of Jupyter Notebook

1. The web application: This provides an interactive interface to write and run the program as well as to authorize documents.

2. Notebook documents: There are various documents which restrain a demonstration of a range of content that is perceptible through the notebook web application, and each of these documents get managed by their kernel. 

3. Kernels: It can run different processes as well as execute different codes written in a given language and returns the compiled result to notebook web-application. It also manages the handling of computations of data related to widgets and graphs that are interactive.

# Data Analysis with Python
## NumPy

NumPy is a commonly used Python data analysis package. By using NumPy, you can speed up your workflow, and interface with other packages in the Python ecosystem, like scikit-learn, that use NumPy under the hood. NumPy was originally developed in the mid 2000s, and arose from an even older package called Numeric. This longevity means that almost every data analysis or machine learning package for Python leverages NumPy in some way.

in this tutorial, we’ll walk through using NumPy to analyze data on wine quality. The data contains information on various attributes of wines, such as pH and fixed acidity, along with a quality score between 0 and 10 for each wine. The quality score is the average of at least 3 human taste testers. As we learn how to work with NumPy, we’ll try to figure out more about the perceived quality of wine.

The data was downloaded from the UCI Machine Learning Repository, and is available here. Here are the first few rows of the winequality-red.csv file, which we’ll be using throughout this tutorial:

```
"fixed acidity";"volatile acidity";"citric acid";"residual sugar";"chlorides";"free sulfur dioxide";"total sulfur dioxide";"density";"pH";"sulphates";"alcohol";"quality"
7.4;0.7;0;1.9;0.076;11;34;0.9978;3.51;0.56;9.4;5
7.8;0.88;0;2.6;0.098;25;67;0.9968;3.2;0.68;9.8;5
```

The data is in what I’m going to call ssv (semicolon separated values) format — each record is separated by a semicolon (;), and rows are separated by a new line. There are 1600 rows in the file, including a header row, and 12 columns.

Before we get started, a quick version note — we’ll be using Python 3.5. Our code examples will be done using Jupyter notebook.

## Lists Of Lists for CSV Data


Before using NumPy, we’ll first try to work with the data using Python and the csv package. We can read in the file using the csv.reader object, which will allow us to read in and split up all the content from the ssv file.

In the below code, we:

* Import the csv library.
* Open the winequality-red.csv file.
    * With the file open, create a new csv.reader object.
        * Pass in the keyword argument delimiter=";" to make sure that the records are split up on the semicolon character instead of the default comma character.
    * Call the list type to get all the rows from the file.
    * Assign the result to wines.

``` 
import csv
with open('winequality-red.csv', 'r') as f:
    wines = list(csv.reader(f, delimiter=';'))
```

Once we’ve read in the data, we can print out the first 3 rows:

``` 
print(wines[:3])

[['fixed acidity', 'volatile acidity', 'citric acid', 'residual sugar', 'chlorides', 'free sulfur dioxide', 'total sulfur dioxide', 'density', 'pH', 'sulphates', 'alcohol', 'quality'], ['7.4', '0.7', '0', '1.9', '0.076', '11', '34', '0.9978', '3.51', '0.56', '9.4', '5'], ['7.8', '0.88', '0', '2.6', '0.098', '25', '67', '0.9968', '3.2', '0.68', '9.8', '5']]

```

The data has been read into a list of lists. Each inner list is a row from the ssv file. As you may have noticed, each item in the entire list of lists is represented as a string, which will make it harder to do computations.

## Numpy 2-Dimensional Arrays
With NumPy, we work with multidimensional arrays. We’ll dive into all of the possible types of multidimensional arrays later on, but for now, we’ll focus on 2-dimensional arrays. A 2-dimensional array is also known as a matrix, and is something you should be familiar with. In fact, it’s just a different way of thinking about a list of lists. A matrix has rows and columns. By specifying a row number and a column number, we’re able to extract an element from a matrix.

In a NumPy array, the number of dimensions is called the rank, and each dimension is called an axis. So the rows are the first axis, and the columns are the second axis.

Now that you understand the basics of matrices, let’s see how we can get from our list of lists to a NumPy array.

## Creating A NumPy Array

We can create a NumPy array using the numpy.array function. If we pass in a list of lists, it will automatically create a NumPy array with the same number of rows and columns. Because we want all of the elements in the array to be float elements for easy computation, we’ll leave off the header row, which contains strings. One of the limitations of NumPy is that all the elements in an array have to be of the same type, so if we include the header row, all the elements in the array will be read in as strings. Because we want to be able to do computations like find the average quality of the wines, we need the elements to all be floats.

In the below code, we:

* Import the numpy package.
* Pass the list of lists wines into the array function, which converts it into a NumPy array.
    * Exclude the header row with list slicing.
    * Specify the keyword argument dtype to make sure each element is converted to a float. We’ll dive more into what the dtype is later on.


## Alternative NumPy Array Creation Methods

There are a variety of methods that you can use to create NumPy arrays. To start with, you can create an array where every element is zero. The below code will create an array with 3 rows and 4 columns, where every element is 0, using numpy.zeros:

```
import numpy as np
empty_array = np.zeros((3,4))

empty_array
```
It’s useful to create an array with all zero elements in cases when you need an array of fixed size, but don’t have any values for it yet.

You can also create an array where each element is a random number using numpy.random.rand. Here’s an example

```
np.random.rand(3,4)

array([[ 0.2247223 , 0.92240549, 0.14541893, 0.61731257],
[ 0.00154957, 0.82342197, 0.74044906, 0.11466845],
[ 0.6152478 , 0.14433138, 0.13009583, 0.22981301]])

```

## Using NumPy To Read In Files

It’s possible to use NumPy to directly read csv or other files into arrays. We can do this using the numpy.genfromtxt function. We can use it to read in our initial data on red wines.

In the below code, we:
* Use the genfromtxt function to read in the winequality-red.csv file.
* Specify the keyword argument delimiter=";" so that the fields are parsed properly.
* Specify the keyword argument skip_header=1 so that the header row is skipped.

``` 
wines = np.genfromtxt("winequality-red.csv", delimiter=";", skip_header=1)
```

wines will end up looking the same as if we read it into a list then converted it to an array of floats. NumPy will automatically pick a data type for the elements in an array based on their format.