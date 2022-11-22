# Laborial-19

**Topic: indexing and lists**

## Introduction
This tutorial is intended to familiarize you with the `list` datatype and methods.

## List methods, functions, and operators
You may find the following methods or functions useful for ex-01. For a given list `a_list`:

| Method or function                            | Description                                          |
|-----------------------------------------------|------------------------------------------------------|
| `a_list = [element0, element1, ... elementN]` | Initializes the list with any number of elements     |
| `a_list.append(element)`                      | Adds the element to the end of the list              |
| `len(a_list)`                                 | Returns the length of the list                       |
| `a_list.insert(i, element)`                   | Inserts the element between position `i` and `i + 1` |
| `del a_list[i]`                               | Removes the element at position `i`                  |
| `a_list.remove(element)`                      | Removes the first instance of `element`              |

Additionally, there are the following list operators:

| Operator            | Description                                                           |
|---------------------|-----------------------------------------------------------------------|
| `a_list[i]`         | Accesses the element at position `i` (read or write, but must exist!) |
| `a_list == b_list`  | Evaluates to `True` if both lists contain the exact same elements     |
| `a_list + b_list`   | Concatenates the two lists together                                   |
| `a_list * N`        | Evaluates to a new list with `a_list` elements repeated `N` times     |
| `element in a_list` | Returns `True` if `element` is in the list                            |

## Exercises

### ex-01: lists of strings

1. Design and implement a Python function named `get_courses` that prompts the user repeatedly for courses, building a **list of strings** containing those courses. It should stop prompting when the user enters a blank line. It should then return the list of courses. 

   Once you've built that function, use it in a simple `main` that calls your function and then displays how many courses were added and a list of the courses as well. Here's an example of the `main` in action:

   <pre>
   Enter the name of a course to add, or press Enter to finish: <b><u>COMP 1501</u></b>
   Enter the name of a course to add, or press Enter to finish: <b><u>MATH 1505</u></b>
   Enter the name of a course to add, or press Enter to finish:
   2 courses added:
   - COMP 1501
   - MATH 1505
   </pre>


2. Assume that your previous function returns the following list:
   ```python
   courses = ["COMP 1501", "Math 1505", "GNED 1401", "GNED 1103", "MKTG 2150",
              "COMP 1502", "COMP 2511", "MGMT 3210", "HRES 2170", "GNED 1101"]
    ```
    > You can split lists across multiple lines to enhance readability.

    Write a new function that takes your course list as an argument and returns the course with the **highest course code**. For this example, the return value of your function should be `"MGMT 3210"`.

    _Hint: `split` sure will come in handy here._

### ex-02: find the bug

Someone has written the following function to remove all courses with a given prefix. However, there's a bug in it. 

```python
def remove_all(courses: list, prefix: str) -> None:
    """Removes all courses matching prefix from the courses list"""

    i = 0
    num_courses = len(courses)

    while i < num_courses:
        if prefix in courses[i]:
            del courses[i]
        i += 1
```

Run the following code and observe what happens.

```python
courses = ["COMP 1501", "GNED 1103", "GNED 1401", "MATH 1505"]
remove_all(courses, "GEOL")
remove_all(courses, "MATH")
remove_all(courses, "GNED")
```

Now answer these questions:

1. Does an error occur every time you call the function? If not, which call(s) seem to be exploding?
   
2. What *kind* of error occurs? The general error types are syntax, runtime, and logic.

3. Trace the code to find the bug. Try to do it by hand, 'cuz VS Code won't be there on your final exam.

4. Can you suggest a fix for this function? Implement it and see if the bug is gone.

5. What additional test values should you consider to fully ensure the function is now working as expected?

### ex-03: grade lists 

Assume you have two lists of quiz grades for a class of students, `quiz1` and `quiz2`. Both lists have an equal number of elements and the element at index i in either list represents the quiz grade for the same student. For example:

```python
quiz_1_grade_list = [
    57,  # student A's quiz 1 grade
    89,  # student B's quiz 1 grade
    92,  # student C's quiz 1 grade
    76   # student D's quiz 1 grade
]

quiz_2_grade_list = [
    87,  # student A's quiz 2 grade
    83,  # student B's quiz 2 grade
    94,  # student C's quiz 2 grade
    74   # student D's quiz 2 grade
]
```

1. Write a Python function that takes the two lists as input parameters and returns a *third* list containing the higher of the two quiz grades for each student. For example, if the 2 lists shown above were passed into the function, it should return this list:

```python
[
    87,  # student A's quiz 2 grade was higher
    89,  # student B's quiz 1 grade was higher
    94,  # student C's quiz 2 grade was higher
    74   # student D's quiz 1 grade was higher
]
```

2. Write another function that takes a list of quiz grades and returns the maximum grade. Do not use the `max` function - exercise those muscles, folks. For example, if the list shown in `1` was passed to the function, it should return **94**.

3. Write another function that takes a list of quiz grades and returns the **index** of the highest grade. For example, if the list shown in `1` was passed to the function, it should return **2**. 

4. Re-write the function from `2` so that it uses your function from `3`.