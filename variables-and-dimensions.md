---
title: 'Variables and Dimensions'
teaching: 10
exercises: 2
---

:::::::::::::::::::::::::::::::::::::: questions 

- How can I store and work on data?
- What does MATLAB assume about your data?
- How can I handle data of 2, 3 or more dimensions?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Understand what a Variable is and how MATLAB handles them
- Learn about slicing and how we can create variables of various dimensions
- Briefly review data types and why they aren't important in MATLAB

::::::::::::::::::::::::::::::::::::::::::::::::

## Introduction

When programming there are many occasions where you will want to be able to access some data, for example you may want to load in a data set from online, load data from an sensor in the field or store the results of a calculation. How we store and refer to data in programming is a variable.


## Variables

A variable in MATLAB is made of 2 parts, a name and a value. The name is what we use to refer to a variable and the value is the number, word, or item that is stored in it. 

The value of a variable in MATLAB can be many things! Some examples are

| Variable Type | Example Value |
|---|---|
|Integer| 1, 2, 3|
|Double| 1.23, 4.56|
|Character| A, b, c|
|String| "hello"|
|Matrix| [1 2 3; 4 5 6]|
|Logical| True, False|

## Workspace

As mentioned in the previous episode, MATLAB has a section called the workspace, this is where you can view what Variables are in-memory. The most simple way of creating a variable is with the '=' symbol, for example:
```
my_variable = 5
```
will create a variable with the name my_variable and a value of 5

::: spoiler
### Memory

MATLAB (like most programming languages), holds variables in-memory. This means they are stored on your computers RAM rather than your hard drive. This allows for fast access and processing, however RAM is wiped when your computer turns off so your workspace will be deleted when you close MATLAB or your computer.
:::

::: challenge
  1. Create a variable called A with a value of 3: `A = 3`
  
  2. Create a variable called B with a value of hello: `B = 'hello'`
  
  3. Create a variable called a with the value of C: `a = 'C'`
  
  4. Customise your workspace and add the extra columns Size, Bytes and Class, this can be done by right clicking the top of the workspace
  
::: solution
  Your workspace should look like this! We suggest customising the workspace columns just as an example of what is possible. 
![](fig/workspace.png){alt="A screenshot of the MATLAB workspace with 3 variables in it from the challenge"}
:::
:::

::: spoiler
### Data Types
You may notice in the previous solution there is a type called a 'double'. MATLAB is whats known as a dynamically typed language, which is also called the fun duck typing. This is based off the saying 'if it walks like a duck and quacks like a duck it's probably a duck'. In programming terms this means that when you make a variable MATLAB has a look at it and assumes what type it is based on how it looks. Other languages like C++ require you to explicitly tell the program what type every variable is.

For you as a user, this means that you don't have to really know or pay attention to data types! However it is worth knowing they exist as if you get more advanced you may want to manipulate them to optimise your algorithms or some other advanced use cases.
:::

::::::::::::::::::::::::::::::::::::: challenge 

## Challenge 1: Can you do it?

What is the output of this command?

```r
paste("This", "new", "lesson", "looks", "good")
```

:::::::::::::::::::::::: solution 

## Output
 
```output
[1] "This new lesson looks good"
```

:::::::::::::::::::::::::::::::::


## Challenge 2: how do you nest solutions within challenge blocks?

:::::::::::::::::::::::: solution 

You can add a line with at least three colons and a `solution` tag.

:::::::::::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::

## Figures

You can use pandoc markdown for static figures with the following syntax:

`![optional caption that appears below the figure](figure url){alt='alt text for
accessibility purposes'}`

![You belong in The Carpentries!](https://raw.githubusercontent.com/carpentries/logo/master/Badge_Carpentries.svg){alt='Blue Carpentries hex person logo with no text.'}

## Math

One of our episodes contains $\LaTeX$ equations when describing how to create
dynamic reports with {knitr}, so we now use mathjax to describe this:

`$\alpha = \dfrac{1}{(1 - \beta)^2}$` becomes: $\alpha = \dfrac{1}{(1 - \beta)^2}$

Cool, right?

::::::::::::::::::::::::::::::::::::: keypoints 

- Use `.md` files for episodes when you want static content
- Use `.Rmd` files for episodes when you need to generate output
- Run `sandpaper::check_lesson()` to identify any issues with your lesson
- Run `sandpaper::build_lesson()` to preview your lesson locally

::::::::::::::::::::::::::::::::::::::::::::::::

