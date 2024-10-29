---
title: 'Working with Variables'
teaching: 10
exercises: 2
---

:::::::::::::::::::::::::::::::::::::: questions 

- How can I fetch data out of a variable?
- How can I change the values of parts of variables?
- What are operations?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Access MATLAB variables and change them
- Use variables to execute mathematical operations and in functions

::::::::::::::::::::::::::::::::::::::::::::::::

## Introduction

So far we have learnt how to create variables of various sizes with different methods. This episode will now focus on how ways we can use variables.

Now is a good time to `clear` and `clc` your workspace and command window!

## Extracting Variables

First lets start by making a dummy variable that we can use as our stand-in dataset.

``` MATLAB
data = 100*rand(6,4);

```

### Subsets

Subsets of values or single values can be extracted from a variable with round brackets `()`

For example to take the value on the third row and second column:
``` MATLAB
data(3,2)
```

We can use colon notation to extract multiple values as well:

``` MATLAB
% Extract columns 1, 2, and 3 on row 3
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
subset2 = data(1,1:2:end)

% Select the first, third and forth rows for all columns, save in subset3
subset3 = data([1 3 4], :)
```

::: callout
### end

When extracting the subset of a matrix, or slicing it, when specifying the range you can use the keyword `end` to represent the last value in a vector (or row or column of a matrix, etc.).
:::

## Altering Variables

As we have seen so far, the object on the left hand side of the equal sign '=' is set to what is on the right hand side. So to change the value of a variable we simply put it on the left:

``` MATLAB
% Set the value on the 3rd row and 2nd column to equal 10
data(3,2) = 10

```

If you look at data in your workspace now you will see that value has been changed!

One use case of altering data may be when you find an erroneous value. For example, if you were looking at a table of reviews out of 5, you may wish to change a rating that was somehow set to above 5 to NAN, to show it was invalid.

``` MATLAB
data(3,2) = NaN
```

### Transpose

One useful tool in manipulating matrices (plural of matrix) in MATLAB is the transpose. This will effectively pivot the matrix so each row becomes a column and each column becomes a row. This is done in MATLAB by adding an apostrophe `'` after a variable:

``` MATLAB
% Transpose data and save it as data_t
data_t = data'
```

You should see that data_t has a flipped size compared to data

### Concatenation

Concatenation is a common operation in data handling. Concatenating means to link or put together, it allows to to take two matricies or variables and add them into a single variable. This is useful for if example your dataset is saved across multiple files.

First let's `clear` our workspace again, create a new data variable and some subsets of the data to work with.

``` MATLAB

clear
data = 100*rand(6,4);

subset1 = data(:,1);
subset2 = data(:,2);

```

Both our subsets are column vectors, if we wanted to concatenate them together into a larger column vector there are three ways

``` MATLAB
new_data = [subset1; subset2]

new_data = cat(1, subset1, subset2)

new_data = vertcat(subset1, subset2)

```
All `[;]`, `cat`, and `vertcat` are all different ways to do the same vertical concatenation.

::: callout

Don't forget if you find a function you aren't familiar with you can use `help` or `doc` to learn more!

:::

::: instructor

This is a good point to use `help cat` and explain how they can learn that the parameters to it are and why you need a 1 at the front. Getting them used to looking up functions and not getting stuck is important!

:::

If we wanted to concatenate the subsets into 1 variable as separate columns we could do

``` MATLAB

new_data2 = [subset1 subset2]

new_data2 = cat(2,subset1,subset2)

new_data2 = horzcat(subset1,subset2)
```

One advantage of using `cat` is that it can work for arrays of larger dimensions, whereas the square bracket shortcut, `vertcat`, and `horzcat` only works for the first two dimensions of the data.

::: challenge

### Challenge 1

### Challenge 1

1. Extract every other row from Data assign it to the varibale name `subset_a`

2. Extract the first four rows from the 2nd column of Data and call it `subset_b`

3. Transpose `subset_b`, call this variable `subset_t`

4. Concatenate `subset_a` and `subset_t` along the first dimension

::: solution
``` MATLAB
% Extract every other row from Data assign it to the varibale name subset_a
subset_a = data(1:2:6,:)

% Extract the first four rows from the 2nd column of Data and call it subset_b
subset_b = data(1:4,2)

% Transpose subset_b, call this varibale subset_t 
subset_t = subset_b'

% Concatenate subset_a and subset_t along the first dimension
new_data3 = cat(1, subset_a, subset_t)
```

`new_data3` should be of size 4x4

:::
:::

## Operations

We're now going to look at some mathematical operations we can perform on our variables.

Before continuing this is a good point to `clear` your workspace again and make a new dummy data variable.
This time we will round each data point to the nearest whole number with the function `round`

``` MATLAB
clear
data = 100 * rand(10,10)

% Round to nearest whole number and overwrite data variable
data = round(data)
```

You may be familiar with the syntax (syntax is a word typically used in programming to mean format) of the most basic operators from other computer programs.



``` MATLAB

data_add = data + 10;
data_subtract = data - 10;
data_divide = data / 10;
data_multiply = data * 10;

```

One common mistake made by users of MATLAB is with the multiply operator. When multiplying pay attention to make sure you are getting the result you expect!

::: challenge

### Challenge 2

### Challenge 2

1. Make a row vector called `row` with values 1, 2 & 3
2. Make a column vector called `column` with values 4, 5 & 6
3. Before trying to multiply them, guess the size of the result of `row * column`
4. Multiply row and column and see if the result is as you expect

::: solution

``` MATLAB

row = [1 2 3];
column = [4; 5; 6];
row * column

```
``` OUTPUT

ans =
    32

```
The resulting variable is a scalar! If you are familiar with matrix multiplication this may make sense to you, don't worry if you are not however.
:::
:::

As seen in the challenge above, by default MATLAB will attempt to perform something called [matrix multiplcation](https://www.google.com/url?sa=t&source=web&rct=j&opi=89978449&url=https://www.sheffield.ac.uk/media/31960/download%3Fattachment&ved=2ahUKEwi64YS815WJAxXRSkEAHUU8BNwQFnoECDUQAQ&usg=AOvVaw22KRaWHu7_55Hec_tvuYxa), you don't need to know about matrix multiplication but it is worth knowing it is the default behaviour.

What you may expect to have been doing is something called [dot multiplication](https://uk.mathworks.com/help/matlab/ref/double.times.html).

``` MATLAB

row2 = [4 5 6];
row.*row2

```
``` OUTPUT
ans =

     4    10    18
```

As the example above shows, dot multiplication multiplies each element of both variables with each other 1 to 1. This is why it is also sometimes called element-wise multiplication.

## Functions
## Functions

Next we will look at some key functions that you may want to use in data analysis and processing

``` MATLAB

% Find the size of a matrix
matrix_size = size(data)

% Add together the rows in each column
column_totals = sum(data, 1)

% Take the mean of the rows in each row
row_means = mean(data, 2)

% Find the maximum value in each column
data_max = max(data)

% Find the minimum value in each row
data_min = min(data, [], 2)

% Find the maximum value of the entire matrix
data_max_all = max(data, [], "all")

```

::: instructor
It is worth exploring why the square brackets exist here, demoing using the help or doc command to find why that exists and use it as a learning example.
:::

::: challenge

### challenge 3

In this challenge we will combine the tools we have learnt so far to compare rainfall data between Sheffield and India

1. Load the datasets from files
``` MATLAB
% Import rainfall data. 
Sheffield_Rain = load('Sheffield_Rain.csv');
India_Rain = load('SouthIndia_Rainfall.csv');
```

2. Investigate the data, open it up in the workspace and understand what is in each column

3 

:::

::::::::::::::::::::::::::::::::::::: keypoints 

- Use `.md` files for episodes when you want static content
- Use `.Rmd` files for episodes when you need to generate output
- Run `sandpaper::check_lesson()` to identify any issues with your lesson
- Run `sandpaper::build_lesson()` to preview your lesson locally

::::::::::::::::::::::::::::::::::::::::::::::::

