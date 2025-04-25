---
title: 'Control'
teaching: 10
exercises: 2
---

:::::::::::::::::::::::::::::::::::::: questions 


- What are the different types of loop and how can they be controlled?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives


- Understand the main types of loop and when they should be used

::::::::::::::::::::::::::::::::::::::::::::::::



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


- for loops for when you know how many iterations to loop, while loops when you don't

::::::::::::::::::::::::::::::::::::::::::::::::

