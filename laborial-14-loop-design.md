# Laborial-14

**Topic: Loop Design**

<!-- Based on COMP 1631 tutorial -->

## Introduction
This tutorial is intended to get you used to designing loops and recognizing common patterns. In small groups, working on the whiteboard or paper, work through the following exercises. You can check your answers using the Python interpreter, but try to solve them by hand first.

## Loop Design Steps
When designing loops, consider the following steps:
1. decide what to iterate (this will be placed in the loop body)
2. decide on a loop control variable (LCV)
3. decide on the terminal condition(s)
4. decide on the initial condition(s)
5. decide how to update the LCV

## Designing Loops

1. Design and write an **algorithm** for a loop which reads 10 integers and prints out the sum of those integers. Use a `while` loop.

    > Start by considering the five loop design steps listed at the top.

1. Re-design your solution to problem 1 so that the loop reads *all* of the integers entered by a user until an **empty string** is input. Once more, print the largest.

    > How do the answers to the five loop design steps change? (Hint: how will you know when you are out of integers?) 

1. Design and write a **Python function** for a loop which reads a sequence of characters (all in lower case), ending in an exclamation mark (e.g. a sentence), and returns the **vowel count**. Again, use a while loop.

    > Start by considering the five loop design steps.

 
## Tracing Loops

1. Consider the following Python code:
    ```python
    choice = int(input("Enter a positive integer >= 2: "))
    num_divisors = 0
    possible_divisor = 2

    while possible_divisor <= choice // 2:
        if choice % possible_divisor == 0:
            print("D", end="")
            num_divisors += 1
        else:
            print(".", end="")
        
        possible_divisor += 1

    if num_divisors == 0:
        print(" prime!")
    else:
        print(f" not prime ({num_divisors} divisors)")
    ```

    Answer the following:
   1. identify the loop body
   2. identify the loop control variable
   3. identify its pre-loop initialization point
   4. identify the loop test
   5. what is the termination condition?
   6. specifically, what would the termination condition be for an input of 7?
   7. identify the update of the loop control variable
   8. what is the common loop pattern?
   9. what problem is this loop solving?

2.  Trace the above for inputs of 11 and then 12.