---
title: 'logic'
teaching: 10
exercises: 2
---

:::::::::::::::::::::::::::::::::::::: questions 

- How can I make my code do different things when variables change?
- How can I compare values in an array to other values?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Learn to use relational operators to compare values
- Understand if and else statements to create conditional code

::::::::::::::::::::::::::::::::::::::::::::::::

## Relational Operators

Relational operators are used to compare the values in 2 arrays and returns a logical array.

Here are the most common logical operators in MATLAB:

``` MATLAB
data == 50 % Are any data points equal to 50?
data ~= 50 % Are any data points not equal to 50?
data > 50 % Are any data points greater than 50?
data < 50 % Are any data points less than 50?
data >= 50 % Are any data points greater than or equal to 50?
data <= 50 % Are any data points less than or equal to 50?

```

Here is an example of comparing two arrays:

``` MATLAB

a = [1 1 1 1];
b = [1 2 1 2];

a == b

```
``` OUTPUT
ans =

  1×4 logical array

   1   0   1   0
```
::: callout

## MATLAB Logic

MATLAB represents logical true and false statements with 1 and 0, where 1 is true and 0 is false

:::

The returned logical array tells us that the first values were equal, the second not equal, etc.

## If Statements

If statements allow us to execute different lines of code depending on a logical value.


``` MATLAB
c = 10

if c > 0
  disp('c is positive')
end
```
``` OUTPUT
c is positive
```

In this example, `c > 0` is called the **condition**, `disp('c is positive')` is 
the code which will be executed if the condition is true, and every if statement 
in MATLAB should be terminated with an `end` 

We can use some inbuilt functions such as `any` or `all` to test a condition across an entire array.

For example, we have a data set representing student marks called data, where each value is a mark out of 100, each row a student and each column a subject:

``` MATLAB
student_marks = round(100*rand(4,6));
```
We could test if any there any marks below or equal to 10 with the following code

``` MATLAB


if any(student_marks < 10)
  disp('Severe failing mark in dataset')
end
```

::: challenge

Using the `student_marks` data above, display a sentence if any student achieves a first (70 or more) in the 3rd subject

::: solution

``` MATLAB

if any(student_marks(:,3) >= 70)
  disp('At least 1 student has achieved a first in subject 3')
end
```
:::
:::

### if else elseif

Conditions can be chained together using the `else` and `elseif` terms. This allows for multiple different code blocks to be used depending on multiple conditions.

``` MATLAB
if all(student_marks(:,2) >= 70)
  disp('All students have a first in subject 2')
elseif any(student_marks(:,2) >= 70)
  disp('At least 1 student has a first in subject 2')
else
  disp('No students have a first in subject 2')
end
```

::::::::::::::::::::::::::::::::::::: keypoints 

- if, elseif and else can be used to create powerful conditions

::::::::::::::::::::::::::::::::::::::::::::::::

