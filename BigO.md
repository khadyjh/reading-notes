# Big O

notation used to describe the efficiency of an algorithm or function. This efficiency is evaluated based on 2 factors:
   - Running Time(Time complexity)

       The amount of time a function needs to complete.
   - Memory Space (space complexity)

        The amount of memory resources a function uses to store data and instructions.

Big O’s in algorithm efficiency describe the Worst Case of efficiency an algorithm can have in performing it’s job. the main factors time and space 

to analyze these factors, we should consider 4 Key Areas for analysis:

1. Input Size

   refers to the size of input reads py the algorithm, not the number of them but the size of each one .

***example :***

     If a function uses an array or list as one parameter, then the number of elements within that array or list will directly increase the Input Size of that parameter.  

     
**the letter " n " to refer to the Input Size value.**

The higher this number, the more likely there will be an increase to Running Time and Memory Space.

2. Units of Measurement

To evaluate a function for Time and Space complexity, we need a way to measure each of these factors.

In order to quantify the Running Time in our analysis, we will consider Three Measurements of time:
- The time in milliseconds from the start of a function execution until it ends.

For the purposes of Big O, we won’t be considering this measurement since different machines will have different individual run times depending on how powerful they are. Regardless, this will always be a measurement of run-time.

- The number of operations that are executed.

Think of this as the number of lines of code that are executed from start to finish of a function.

- The number of “Basic Operations” that are executed.

“Basic Operation” refers to the operation that is contributing the most to the total running time. This is usually the most time consuming operation within the inner most loop.


In order to quantify Memory Space, we can consider this Sources of Memory Usage during function run-time:

- The amount of space needed to hold the code for the algorithm.

Think of this as the number of bytes required to store the characters for the instructions specified in your function.

- The amount of space needed to hold the input data.

If direct input data is not considered, we may just refer to this as Additional Memory Space since not all functions have direct input values.


- The amount of space needed to hold working space during the calculation.

Working Space can be thought of as the creation of variables and reference points as our function performs calculations. This will also include Stack Space of recursive function calls … specifically how memory usage scales relatively with the size of the input.




3. Orders of Growth

- Constant Complexity means that no matter what inputs are thrown at our algorithm, it always uses the same amount of time or space. The number 1 is used to represent a constant value. The actual number of units will most likely be greater than 1, we round this number down to 1 to represent our estimate of complexity that is independant of n.

***example :***

```
This algorithm has an O(1) constant efficiency, no matter the size of a or b, this function simply returns the sum of those 2 numbers.

ALGORITHM Sum(number a, number b)

   number val <-- a + b
   return val

```

resources 

[Big O](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-05/resources/big_oh.html)
