# Laborial-17

**Topic: Strings, indexing, while and for loops**

## Instructions

The following exercises will give you experience looping through strings using both while and for loops. 

## Exercises

### ex-01: shoutiness calculator 

_Shoutiness_ is a word I just made up that expresses how LOUD a string is, calculated by taking the number of CAPITAL LETTERS IN THE STRING and dividing it by the length of that string.

For example:

```python
"YO, WHAT IS UP?" # 10 capital letters / length of 15 = 0.66666... shoutiness

"i am meek" # 0 capital letters / length of 9 = 0 shoutiness

"No, I'M Sparticus!" # 4 capital letters / length of 18 = 0.2222... shoutiness

"" # assume the empty string is 0 shoutiness
```

Write a function with a reasonable name that takes in a string and returns its shoutiness. To build your coding muscles, do this once using a **while loop** and then again with a **for loop**.

> This is _pretty_ similar to the vowel-counting we did in lecture yesterday...but watch out that you handle that empty string situation properly!

You can use the [isupper method](https://docs.python.org/3/library/stdtypes.html#str.isupper) to help you here.


### ex-02: vowel Roomba

You've just got a software development gig for a person who simply _hates_ vowels. I mean, they totally _despise_ those poor, innocent letters.

You need the cash, so figure you'll take the fls mny.

Create a function with a reasonable name that takes in a string and returns a different version of that string (remember, strings are **immutable**) without any vowels. You can assume that vowels do not include y. Ideally, you should do this once using a **while loop** and once with a **for loop**, if only to gain an appreciation of how nice a for loop can be - in certain situations.

Your function should detect both lower and uppercase vowels.

```python
# if the string used is this...
"what I do have are a very particular set of skills" 

# ...your function should return this
"wht  d hv r  vry prtclr st f sklls"
```

> This might be a good chance to use that funky vowel-detection code from yesterday's lecture.

Gd lck!


### ex-03(trickyish): XOdecimal

> _Although the for loop is pretty awesome, sometimes a while loop can lend itself to a solution more easily. It's best not to pooh-pooh something in a language - I've invariably found that my disdain was ill-informed._

In this exercise, you will need to make a function that converts a string representing an _XOdecimal number_ into its integer value. Yes, _XOdecimal_ is another word I've made up.

In XOdecimal, instead of the digits 0 through 9, there are only 3 types of digits: 'x', 'o', and everything else. 'x' has a value of 1, 'o' has a value of 0, and everything else has a value of -1.

Instead of explaining some complicated rules to explain how to calculate the value of an XOdecimal number into an integer in English, I think showing you a few examples will be clearer:

```text
# work from right-hand side of string to left
"xo" is equivalent to: (0 * 1) + (1 * 10) = 10

"xxx" is equivalent to: (1 * 1) + (1 * 10) + (1 * 100) = 111

"yo" is equivalent to: (0 * 1) + (-1 * 10) = -10

"xoyx" is equivalent to: (1 * 1) + (-1 * 10) + (o * 100) + (1 * 1000) = 991
```

I'd suggest using a while loop to do this exercise.
