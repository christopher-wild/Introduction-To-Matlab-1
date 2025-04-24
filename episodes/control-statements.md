---
title: 'Logic and Control'
teaching: 10
exercises: 2
---

:::::::::::::::::::::::::::::::::::::: questions 

- How can I make my code do different things when variables change?
- How can I reuse code in a loop?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Explain how to use markdown with the new lesson template
- Demonstrate how to include pieces of code, figures, and nested challenge blocks

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

An example of one in use would be

``` MATLAB

a = [1 1 1 1];
b = [1 2 1 2];

a == b

ans =

  1×4 logical array

   1   0   1   0
```
::: callout

## MATLAB Logic

MATLAB represents logical true and false statements with 1 and 0, where 1 is true and 0 is false

:::

The returned logical array tells us that the first values were equal, the second not equal, etc.




::::::::::::::::::::::::::::::::::::: keypoints 

- Use `.md` files for episodes when you want static content
- Use `.Rmd` files for episodes when you need to generate output
- Run `sandpaper::check_lesson()` to identify any issues with your lesson
- Run `sandpaper::build_lesson()` to preview your lesson locally

::::::::::::::::::::::::::::::::::::::::::::::::

