# Laborial-17

**Topic: Strings, indexing, while and for loops**

## Instructions

The following exercises will give you experience looping through strings using both while and for loops. 

## Exercises

### ex-01: shoutiness calculator 

The _shoutiness_ is a word I just made up that expresses how LOUD a string is, calculated by taking the number of CAPITAL LETTERS IN THE STRING and dividing it by the length of that string.

For example:

```python
"YO, WHAT IS UP?" # 10 capital letters / length of 15 = 1.5 shoutiness

"i am meek" # 0 capital letters / length of 9 = 0 shoutiness

"No, I'M Sparticus!" # 4 capital letters / length of 18 = 0.2222...s

"" # assume the empty string is 0 shoutiness
```

Write a function with a reasonable name that takes in a string and returns its shoutiness. To build your coding muscles, do this once using a while loop and then again with a for loop.

> This is _pretty_ similar to the vowel-counting we did in lecture yesterday...but watch out that you handle that empty string situation properly!

You can use the [isupper method](https://docs.python.org/3/library/stdtypes.html#str.isupper) to help you here.


### ex-02: vowel Roomba

You've just got a software development gig for a person who simply _hates_ vowels. I mean, they totally _despise_ those poor, innocent letters.

You need the cash, so figure you'll take the fls mny.

Create a function with a reasonable name that takes in a string and returns a different version of that string (remember, strings are **immutable**) without any vowels. You can assume the vowels are aeiou. No y. Ideally, you should do this once using a while loop and once with a for loop, if only to gain an appreciation of how nice a for loop can be - in certain situations.

Your function should detect both lower and uppercase vowels.

```python
# if the string used is this...
"what I do have are a very particular set of skills" 

# ...your function should return this
"wht  d hv r  vry prtclr st f sklls"
```

> This might be a good chance to use that funky vowel-detection code from yesterday's lecture.

Gd lck!


### ex-03: perIODic uppPERcasING

Although the for loop is pretty awesome, sometimes a while loop can lend itself to a solution more easily. It's best not to pooh-pooh something in a language - I've found invariably that thing I scorned actually is pretty useful. Sometimes.

Make a function that takes in a string and a positive integer, n. It should return another version of that string, but with the letter at every multiple of n capitalized. If n is 0, then just return the string, unaltered.

```python
# assume function is called fun
fun("whassup?", 3) # should return "whaSsuP?"
fun("I like lamp", 5) # should return "I likE lamP"
fun("boot scoot", 1) # should return "bOOT SCOOT"
fun("lower", 0) # should return "lower"
```

If you find this too easy, for an extra challenge, ignore spaces in your function - pretend they're not even there:

```python
# assume function is called fun
fun("whassup?", 3) # should return "whaSsuP?"
fun("I like lamp", 5) # should return "I like lamp"
fun("boot scoot", 1) # should return "bOOT SCOOT"
fun("lower", 0) # should return "lower"
```

You will want to use the [upper method](https://docs.python.org/3/library/stdtypes.html#str.upper) available in Python.