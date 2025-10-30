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

::: callout
### Tip: GUI Navigation

You can also change the working directory by clicking on the folder path shown in the Current Folder panel and typing a new path, or by navigating using the folder browser.
:::

### Path File Separators

Linux, Mac and MATLAB Online use forward slashes `/` to separate files where Windows use backslashes `\`.

::: tab
### Windows
```matlab
cd('users\myusername\documents')
```
### Linux/Mac
```matlab
cd('users/myusername/documents')
```

:::

MATLAB has a handy way of allowing you to create paths that can work on both file systems, using the `filesep`

::: tab
### Windows
```matlab
['users',filesep,'myusername',filesep,'documents']
```
```output
'users\myusername\documents'
```

### Linux/Mac

```matlab
['users',filesep,'myusername',filesep,'documents']
```
```output
'users/myusername/documents'
```
:::

This will allow you to share code with colleagues no matter what operating system they are on.


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

Download the [rain_data.mat][rain_data] for the next examples


```matlab
load('rain_data.mat')  % Loads all variables from the file
```

You can also load specific variables:

```matlab
clear

load('rain_data.mat', 'india_data')
```

## Saving Files

### Saving to MATLAB Format

The `save` command stores variables to `.mat` files.

By default the `save` command will save all variables in your workspace:

```matlab
x = 1:10;
y = x.^2;

save('results.mat')
```

To save specific variables:

```matlab
save('results.mat','x','y')
```


:::callout
### When and why use .mat files?
MATLAB's `.mat` format is compressed and optimised for MATLAB data types, so is 
often a good choice if your data is being saved for working in MATLAB. The format 
also preserves the information about data types and dimensions for  your variables.

If you want to save your data to share with colleagues not using MATLAB or to load into other programs like Excel, 
saving to a more open format like `.csv` may be more appropriate.

:::

### Saving to .csv

To save to a `.csv` file that can be read by other programs:

```matlab
data = [1, 2, 3; 4, 5, 6; 7, 8, 9];
writematrix(data,'output.csv')
```

::::::::::::::::::::::::::::::::::::: keypoints 
- Use `pwd` to check your current directory and `cd` to change it
- `readmatrix` to load data from text, CSV, and Excel files
- `load` and `save` work with MATLAB's efficient `.mat` format
::::::::::::::::::::::::::::::::::::::::::::::::

[rain_data]: data/rain_data.mat
