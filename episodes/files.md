---
title: 'Files'
teaching: 10
exercises: 2
---

:::::::::::::::::::::::::::::::::::::: questions

- How do I read data from files in MATLAB?
- How do I save my results to files?
- What file formats does MATLAB support?

::::::::::::::::::::::::::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::: objectives

- Learn to navigate the file system using MATLAB commands
- Understand how to load data from common file formats
- Practice saving variables and results to files

::::::::::::::::::::::::::::::::::::::::::::::::


## Introduction

Working with files is essential for any data analysis workflow. In this episode, we'll learn how to access files in MATLAB, load data from various file formats, and save our results for future use.

## Understanding the Working Directory

MATLAB operates from a specific location on your computer called the **working directory** or **current folder**. This is the default location where MATLAB looks for files and saves new ones.

To see where you currently are, use:

```matlab
pwd
```

This command prints the working directory (hence the name: **p**rint **w**orking **d**irectory).

To change to a different directory, use:

```matlab
cd('path/to/your/folder')
```
## Path File Separators
::: callout
### Tip: GUI Navigation

You can also change the working directory by clicking on the folder path shown in the Current Folder panel and typing a new path, or by navigating using the folder browser.
:::

## Listing Files

To see what files are in your current directory, use:

```matlab
dir
```

This will display all files and folders in your working directory. You can also list files matching a specific pattern:

```matlab
dir('*.csv')  % Lists all CSV files
dir('*.mat')  % Lists all MATLAB data files
```


## Loading Files

### Text and CSV Files

MATLAB can easily read CSV (comma separated value), other text files and spreadsheets using `readmatrix`:

```matlab
sheffield_rain = readmatrix('Sheffield_Rain.csv')
```

### MATLAB Data Files

MATLAB has its own file format with the `.mat` extension. These files can store multiple variables efficiently:

```matlab
load('rain_data.mat')  % Loads all variables from the file
```

You can also load specific variables:

```matlab
load('rain_data.mat', 'india_data')
```

::::::::::::::::::::::::::::::::::::: keypoints 

- pass

::::::::::::::::::::::::::::::::::::::::::::::::

