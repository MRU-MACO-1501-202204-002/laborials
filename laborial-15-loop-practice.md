# Laborial-15

**Topic: Loop Practice**

## Introduction
The goal of this lab is to gain more experience with loops, including counted loops, sentinel loops and nested loops.

## Basic Loops

1. Write a short Python program which reads an integer "lower bound" and an integer "upper bound" from the user, and then displays all odd integers between these bounds (inclusive).

    Use the `while` syntax.

    A sample run of the program might look like:

    <pre>
    enter lower bound: <span style="color: green">8</span>
    enter upper bound: <span style="color: green">15</span>

    9
    11
    13
    15</pre>

1. Write a short Python program which reads a single letter, then a sequence of letters (one letter per line) terminated by a period. It then writes the number of times the given letter occurred in the sequence.

    You may assume the user input is valid, i.e. assume that when a letter is requested the user actually enters a letter character.  It is not necessary to add error handling, although you may wish to incorporate this if you have time.

    A sample run of the program might look like:

    <pre>
    enter letter: <span style="color: green">a</span>
    enter sequence of letters:

    <span style="color: green">b</span>
    <span style="color: green">a</span>
    <span style="color: green">z</span>
    <span style="color: green">z</span>
    <span style="color: green">a</span>
    <span style="color: green">r</span>
    <span style="color: green">.</span>

    count of 'a' occurrences = 2</pre>

    What type of loop pattern should you use to solve this problem?

1. Write a program that prints the first 8 lines of the multiplication table up to 12 - i.e print:

    ```plaintext
    1  2  3  4  5  6  7  8  9 10 11 12
    2  4  6  8 10 12 14 16 18 20 22 24
    3  6  9 12 15 18 21 24 27 30 33 36
        . . .
   12 24 36 48 60 72 84 96 108 120 132 144 
    ```
    
    Don't worry about formatting.

    _Hint: Write a function that uses a loop to write a single row of the output. Than call THAT function repeatedly using **another** loop in **another** function._ 

## More Challenging

Design and write a complete Python program that prompts the user for a base, and then prints an isosceles triangle with that base width. If the input is **even** or **negative** then the program must terminate with an appropriate error message. For example:

```text
enter base (must be positive and odd):5

*
***
*****
```

For now, ignore error checking – you can add that later.

As always, a good way to help in problem solving is to draw pictures, and to see what should happen with sample data (e.g. we have shown you 5 – draw 7 and 9). Examine the required output to find the patterns of what must happen.

Come up with a high-level solution in pseudocode, then design and implement the code. 