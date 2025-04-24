---
title: 'Logic and Control'
teaching: 10
exercises: 2
---

:::::::::::::::::::::::::::::::::::::: questions 

- How can I make my code do different things when variables change?
- How can I compare values in an array to other values?
- What are the different types of loop and how can they be controlled?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Learn to use relational operators to compare values
- Understand if and else statements to create conditional code
- Understand the main types of loop and when they should be used

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

## Loops

Loops in coding allow for blocks of code to be executed multiple times depending on some logic. 
This can save you from having redundant copy and pasted code, making your code shorter and easier to read.

There are two main loop types in MATLAB, for loops and while loops. 
A for loop repeats a specified number of times, a while loop repeats until a logical condition is met.


### For Loops

For loops have the following syntax

```
for index = values
  code
end
```

`values` is typically a vector where the length will define the number of repetitions

`index` will be the current value of values for this iteration. In the exaple below,

``` MATLAB
A = 1:5;
for ii = A
  disp(ii)
end

``` OUTPUT
1
2
3
4
5
```

In this example our `values` is `1:5` which if you remember from indexing produces a vector `[1 2 3 4 5]`

So our for loop, loops 5 times, the first loop our index `ii` will be 1, then 2, etc.

::: challenge

Create a for loop that sums the even numbers in the range 0 to 20. 

::: hint
Try creating another variable called total equal to 0, for each iteration of the loop add the current index

Also think back to previous episodes where we covered indexes and counting in steps
:::

::: solution

``` MATLAB
total = 0
for ii = 0:2:20
  total = total + ii;
end
```
:::
:::

### While Loops

As previously mentioned, while loops will loop while a logical condition is being met. 

``` MATLAB
ii = 0
while ii < 10
  ii = ii + 1;
end
```

Interestingly, as 1 is logic true in MATLAB, the following loop will run until cancelled or MATLAB runs out of resources


::: callout
## Cancel execution
While loops can get stuck in an infinite cycle, to stop this running without shutting MATLAB you can press Ctrl+C or on Mac Ctrl+Break
:::

``` MATLAB
ii = 0
while 1
  ii = ii + 1;
end
```

While loops are useful when you don't know how many iterations are needed. Some common use cases are:

- Iterative Algorithms: Gradient-descent in machine learning, power series
- Event driven: Continuously reading from a sensor, waiting for user input


### Loop Controls

`break` and `continue` are statements that can be used to control behavior in a loop

The `break` statement immediately exits the loop it's in, skipping any remaining iterations. Execution continues with the next statement after the loop.

``` MATLAB
for ii = 1:10
    if ii == 5
        break;
    end
    disp(ii);
end
disp('Loop finished');
```
``` OUTPUT
1
2
3
4
Loop finished
```

The `continue` statement skips the remaining code in the current iteration and jumps to the next iteration of the loop.

``` MATLAB
for ii = 1:8
    if mod(ii, 2) == 0 % Check for even numbers
        continue; 
    end
    disp(ii);
end
```
``` OUTPUT
1
3
5
7
```

::::::::::::::::::::::::::::::::::::: keypoints 

- if, elseif and else can be used to create powerful conditions
- for loops for when you know how many iterations to loop, while loops when you don't

::::::::::::::::::::::::::::::::::::::::::::::::

