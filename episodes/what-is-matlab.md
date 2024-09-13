---
title: 'what-is-matlab'
teaching: 10
exercises: 2
---

::: questions 

- What does MATLAB do?
- How can MATLAB help my Research?

:::

::: objectives

- Explain what tasks MATLAB is well suited for
- Explain how MATLAB compares to other common tools (Python, R)

:::

## Introduction

What is MATLAB?

MATLAB is a high-level propriety programming language and interactive environment primarily designed for numerical computing, data analysis, and scientific visualization. It provides a comprehensive suite of tools for tasks such as matrix manipulation, algorithm development, data plotting, and interfacing with other programming languages. Its user-friendly interface and extensive library of functions make it a popular choice among researchers, engineers, and scientists.


::: callout
### Propriety

MATLAB is a propriety language, this means it is owned by a specific company MathWorks.
Therefore it's source code is not public ally available (opposite of open-source)
and the software is licensed for use under specific terms and conditions. There are many pros and cons of working with propriety software

:::

## Why MATLAB?

While many research tools can accomplish tasks similar to MATLAB, understanding MATLAB's strengths and weaknesses in comparison is important.
Two of the main alternative languages you may have heard of are [Python](https://www.python.org/) and [R](https://www.r-project.org). These are often compared because all 3 languages are often used for 

::: spoiler
### High-Level and Low-Level
Low-level code languages are closer to the machine's language, requiring more precise instructions for the computer to understand. They offer greater control over hardware but are more complex to write and debug. High-level code languages are more abstract and human-readable, translating complex instructions into simpler machine code. They are easier to learn and maintain but may sacrifice some performance efficiency compared to low-level languages.

MATLAB is considered on the high-level end of languages, making it relatively easy to read and work with.

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

