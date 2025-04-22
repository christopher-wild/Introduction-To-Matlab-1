---
title: 'Plotting'
teaching: 10
exercises: 2
---

:::::::::::::::::::::::::::::::::::::: questions 

- How can I visualise my data to explore it and gain insights?
- What types of plot does MATLAB support?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Demonstrate how to create plots in MATLAB that have titles, labelled axis and multiple lines
- Demonstrate how to include pieces of code, figures, and nested challenge blocks

::::::::::::::::::::::::::::::::::::::::::::::::

## Plot Function

MATLAB has an inbuilt function called `plot` that creates 2-D line plots. We will start by exploring how to use this function to get used to
the plotting syntax of MATLAB and how we can explore figures.

::: challenge

## Basic Plot

Create a basic 2D line plot with the following variables

``` MATLAB

x = [1 2 3 4 5];
y1 = [2 4 6 8 10];

plot(x,y1)

```

::: solution

![](fig/plot1.png){alt="A screenshot of a MATLAB figure containing a straight line"}

:::
:::


### hold on

To add another line to the same plot we can use the [hold on](https://uk.mathworks.com/help/matlab/ref/hold.html) command, this will retain the current figure when adding new plots.

::: challenge

## hold on

Create another vector variable called y2 with values 1, 4, 9, 16, 25

1. Plot x against y1 then x against y2 without hold on, what happens?

2. Plot x against y1, then `hold on`, then x against y2, what's different?

::: solution

1. You should only see the y2 line, as the y1 figure was overwritten without `hold on`
![](fig/plot2.png){alt="A screenshot of a MATLAB figure containing a curved"}

2. Now you should have both lines on the same plot
![](fig/plot3.png){alt="A screenshot of a MATLAB figure containing both a straight and curved line"}

:::
:::

::::::::::::::::::::::::::::::::::::: keypoints 

- Use `.md` files for episodes when you want static content
- Use `.Rmd` files for episodes when you need to generate output
- Run `sandpaper::check_lesson()` to identify any issues with your lesson
- Run `sandpaper::build_lesson()` to preview your lesson locally

::::::::::::::::::::::::::::::::::::::::::::::::

