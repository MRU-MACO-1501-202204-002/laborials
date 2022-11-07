# Laborial-15

**Topic: Loop Practice**

## Introduction
The goal of this lab is to gain more experience with loops, including counted loops, sentinel loops and nested loops.

## Basic Loops

### ex-01: counted loop

Write a short Python program which reads an integer "lower bound" and an integer "upper bound" from the user, and then displays all odd integers between these bounds (inclusive).

Use the `while` syntax.

A sample run of the program might look like:

<pre>
enter lower bound: <span style="color: green">8</span>
enter upper bound: <span style="color: green">15</span>

9
11
13
15</pre>

### ex-02: sentinel loop

Write a short Python program which reads a single letter (we'll call it the **_target letter_**), then a sequence of letters (one letter per line) terminated by a period. It then writes the number of times the target letter occurred in the sequence.

You may assume the user input is valid, i.e. assume that when a letter is requested the user actually enters a letter character.  It is not necessary to add error handling, although you may wish to incorporate this if you have time.

A sample run of the program might look like:

<pre>
enter target letter: <span style="color: green">a</span>
enter sequence of letters:

<span style="color: green">b</span>
<span style="color: green">a</span>
<span style="color: green">z</span>
<span style="color: green">z</span>
<span style="color: green">a</span>
<span style="color: green">r</span>
<span style="color: green">.</span>

count of 'a' occurrences = 2</pre>

### ex-03: counted loop in a counted loop

Write a program that prints the first 10 lines of the multiplication table up to 12 - i.e print:

```plaintext
1  2  3  4  5  6  7  8  9 10 11 12
2  4  6  8 10 12 14 16 18 20 22 24
3  6  9 12 15 18 21 24 27 30 33 36
    . . .
10 20 30 40 50 60 70 80 90 100 110 120 
```

Don't worry about formatting.

_Hint: Write a function that uses a loop to write a single row of the output. Than call THAT function repeatedly using **another** loop in **another** function._ 