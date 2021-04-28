# Chapter 2: Creating your first dataframe

In this chapter, we will go through the fundamental steps in constructing your own 
tables. We will examine the command **DataFrame** and **read_csv** and go through 
how we can convert different types of data into a dataframe.

## Why DataFrame?

Before we start, one may question what is so special about **DataFrame**. Dataframe is 
the main type of object used in Pandas. Tables are stored and processed as different
dataframes. In order to benefit the many powerful options available in Pandas, 
the table data needs to be stored in a dataframe variable. 

In Pandas, another main datatype is called **Series**. It is in general a one-dimensional
array data with each entry corresponding to a key. Therefore a series can be viewed
as a slice of a dataframe. Since most options available in series are a subset of that 
of the DataFrame, we do not explicitly discuss series in this book. 

## Build a table from a dictionary

Now let us assume this scenario. You have a table as following (Table 1). The table 
contains data of the amount of fruits in different shops. Instead of using the more 
familiar Microsoft Excel to handle, you want to experiment with Pandas and see what 
you can do with this package.

Table 1: Fruit amount surveyed in different shops

| Shop | Apple | Orange | Kiwi |
| ---- | ----- | ------ | ---- |
|  A   |  18   |   23   |  30  |
|  B   |  23   |   18   |  29  |
|  C   |  31   |   37   |  30  |

The first step is to pass this set of data. The first way is to make this set of data
into a dictionary. Then we make a dataframe object by passing the dictionary into 
this object, namely

```python
df = pandas.DataFrame(dictionary, index=..., columns=...)
```

The first input is compulsory, it can be an iterable such as a list, array or dictionary.
Here we consider a dictionary first. There are a number of auxillary setting you can
pass during declaration, or can be set after the declaration. Here we consider the 
simplest case first. 

To make the above Table 1 into a dictionary which can be converted into a dataframe 
directly, we used the following code:

```python
import pandas as pd       # if not imported Python has no idea what DataFrame means!
data = {
  "Shop":["A","B","C"],
  "Apple":[18,21,31],
  "Orange":[23,18,37],
  "Kiwi":[30,29,30]
}
df = pd.DataFrame(data)
```

You might notice that in preparing the dictionary, we set the keys to be the header of 
all columns. The values for each key correspond to all values under that header. And notice
that the dataframe can contain numerical and alphabetical input.

The results of df can be immediately checked by printing the object out.

|![Results of df](https://github.com/scleung-astro/learning_pandas_from_zero/blob/main/figures/chapter2_fig1.png)|
|-|
|Figure 1: Output of the dataframe df|

One thing to notice is that Pandas by default assign integers 0, 1, 2 and so on as 
the keys for the entry when there is no specification during declaration. We will 
return to this later in this chater. 

If you get the same as that shown in Figure 1, congratulations! This is the very first
step of your first experience in Pandas. 

When we check the variable type of df by typing
```
type(df)
```
we will receive the class 'pandas.core.frame.DataFrame'.

## Build a table from a list

The flexibility of Pandas allows us to choose other types of iterable for passing 
the data. Now we repeat the process by creating a list containing the data. We will
use the following code to construct a list and then pass the list to the dataframe
object.

```python
import pandas as pd       
data = [
  ["A",18,23,30],
  ["B",21,18,29],
  ["C",31,37,30]
]
column_names = ["Shop", "Apple", "Orange", "Kiwi"] 
df = pd.DataFrame(data, columns=column_names)
```

By glancing at the code, there are four major differences compared to the above code for
using dictionary, including:  

1. The square bracket (obvious but easy to miss)  
2. Each entry in the list corresponds to the data from the same row 
3. No column names passed in the list 
4. The column names stored in a separate list

The result dataframe will be identical to Figure 1. Again, this will be very helpful 
to practice once on your own the whole dataframe declaration!

### What if we omit column setting?



### Other common declaration setting

From the example of the list, it becomes clear that the setting of *columns=column_names*
are responsible for sett


### Other types of data available

It is also possible to pass a JSON type data, as it has a structure very similar to a 
dictionary, to create a dataframe. However, we do not discuss the detailed process
as treating JSON type data will involve further notation used in *json* module 
and other web fetching interface in order to achieve a complete discussion. 

## Build a dataframe from a csv file


## Build a dataframe from an excel file

## Exercises 




