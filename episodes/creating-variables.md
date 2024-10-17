---
title: 'Creating Multidimensional Variables'
teaching: 10
exercises: 2
---

::: questions 
- How can I create larger variables?


:::

::: objectives

- temp

:::

## Introduction
This episode will explore for advanced techniques for making variables and look at some useful premade code (functions) that can help us. 

## Slicing

### Colon Notation

MATLAB provides what is called the colon notation which allows us to specify a range of values.

``` MATLAB
a = [1:10]
```
``` OUTPUT
a =

     1     2     3     4     5     6     7     8     9    10
```

`a` should be 1x10 size, meaning 1 row 10 columns

&nbsp;


### Steps
You can also specify a step, so the colon notation only makes every nth number 

``` MATLAB

b = [1:2:20]

```

``` OUTPUT

b =

     1     3     5     7     9    11    13    15    17    19
```

## Functions

We can also use functions to create arrays. Functions are premade code blocks that serve a commonly wanted functionality.

First we will use one called linspace, which stands for linearly spaced. It creates a vector of linearly spaced numbers, you specify the start, end and how many numbers.

::: callout

If you are ever unsure about a function MATLAB has inbuilt help and documentation!

The help command will give a brief text description about the function and how to use it
``` MATLAB
help linspace
```

The doc command will give a more detailed description including examples
``` MATLAB
doc linspace
```

:::

``` MATLAB

c = linspace(1,10,5)

```

``` OUTPUT

c =

    1.0000    3.2500    5.5000    7.7500   10.0000
    
```

Some other useful functions are:
``` MATLAB
% Rand creates an n-dimensional array of random numberes between 0 and 1.
d = rand(5,1)

% Create matrix of 0's
e = zeros(2,2)

% NaN means 'Not a Number', this is a special and useful term for when a value can't be represented by a number. 
f = nan(5,5)
```
::: callout

Here are some common scenarios where NaN may be used:

- Mathematical operations that cant be computed (division by 0, root of negative numbers)
- No data was recorded, for example a in-field sensor may have lost power

:::

::: challenge

1. Create a vector with numbers 12 to 100 containing every 4th number (steps of 4), call it g
2. Create a matrix of random numbers with 4 rows and 5 columns, call it h

::: solution
``` MATLAB
g = 12:4:100
or
g = linspace(12,100,23)
```
:::

:::

## Extracting and Alterating Variables

Now is a good time to **clear** and **clc** your workspace and command window!

First lets start by making a dummy variable that we can use as our stand-in dataset.

``` MATLAB
data = 100*rand(6,4);

```

### Extracting values

Subsets of values or single values can be extracted from a variable with round brackets `()`

For example to take the value on the third row and second column:
``` MATLAB
data(3,2)
```

We can use colon notation to extract values as well:

``` MATLAB
% Extract columns 1,2,3 on row 3
data(3,1:3)
```
A single colon with no numbers will select all

``` MATLAB
% Select all rows in the second column
data(:,2)
```
Some more examples bringing together the tools we've seen so far:

``` MATLAB
% Extract the first 4 rows and all columns and save it in the variable subset1
subset1 = data(1:4,:) 

% Select every other column in the first row, save in subset2
subset2 = data(1,1:2:6)

% Select the first, third and forth rows for all columns, save in subset3
subset3 = data([1 3 4], :)
```

### Altering Variables

As we have seen so far, the object on the left hand side of the equal sign '=' is set to what is on the right hand side. So to change the value of a variable we simply put it on the left:

``` MATLAB
% Set the value on the 3rd row and 2nd column to equal 10
data(3,2) = 10

```

If you look at data in your workspace now you will see that value has been changed!

One use case of altering data may be when you find an erroneous value. For example if you were looking at a table of reviews out of 5, you may wish to change a rating that was somehow set to above 5 to NAN, to show it was invalid.

``` MATLAB
data(3,2) = NaN
```

### Transpose

One useful tool in manipulating matrices (plural of matrix) in MATLAB is the transpose. This will effectively pivot the matrix so each row becomes a column and each column becomes a row. This is done in MATLAB by adding an apostrophe after a variable:

``` MATLAB
% transpose data
data_t = data'
```

You should see that data_t has a flipped size compared to data

### Concatenation

Concatenation (also called concat or cat) is a common operation in data handling. Concatenating means to link or put together, it allows to to take two matricies or variables and add them into a single variable. This is useful for if example your dataset is saved across multiple files.

First let's clear our workspace again, create a new data variable and some subsets of the data to work with.

``` MATLAB

data = 100*rand(6,4);

subset1 = data(:,1);
subset2 = data(:,2);

```

Both our subsets are column vectors, if we wanted to concaternate them together into a larger column vector there are 2 ways

``` MATLAB
new_data = [subset1; subset2];

new_data = cat(1, subset1, subset2)

```
::: callout

Don't forget if you find a function you aren't familiar with you can use `help` or `doc` to learn more!

:::

::: instructor

This is a good point to use `help cat` and explain how they can learn that the parameters to it are and why you need a 1 at the front. Getting them used to looking up functions and not getting stuck is important!

:::

If we wanted to concat the subsets into 1 variable as separate columns we could do

``` MATLAB

new_data2 = [subset1 subset2]

new_data2 = cat(2,subset1,subset2)
```

One advantage of using cat is that it can work for arrays of larger dimensions, where the square bracket shortcut only works for up to 2D data.

::: challenge

1. Extract every other row from Data assign it to the varibale name subset_a

2. Extract the first four rows from the 2nd column of Data. Call it subset_b

3. Transpose subset_b, call this variable subset_t 

4. Concatenate subset_a and subset_t along the first dimension

::: solution
``` MATLAB
% Extract every other row from Data assign it to the varibale name subset_a
subset_a = Data(1:2:6,:)

% Extract the first four rows from the 2nd column of Data. Call it subset_b
subset_b = Data(1:4,2)

% Transpose subset_b, call this varibale subset_t 
subset_t = subset_b'

% Concatenate subset_a and subset_t along the first dimension
newdata = cat(1, subset_a, subset_t)
```

newdata should be of size 4x4

:::

:::

::: keypoints 

 - point 1
:::

