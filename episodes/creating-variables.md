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

## Indexing

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



::: keypoints 

 - point 1
:::

