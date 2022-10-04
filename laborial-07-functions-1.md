# Laborial-07

**TOPIC: Functions**

## Part 1: Basics

Use this code for the next 2 questions:

```python
def test(a, b, c):
    print(a, b, c)

def main():
    a = 1
    b = 2
    c = 3
    test(a, b, c)
    test(b, a, c + 7)

main()
```

1. Identify the following items in the code above:

    1. function headings
    2. function bodies
    3. function definitions
    4. function calls
    5. function arguments
    6. function parameters
    7. local variables

2. Fill in the table below with the values of the parameters `a`, `b`, and `c` *inside* the `test` function used in the code above for each of the two function calls to `test`:

    | Call to `test` | `a` | `b` | `c` |
    | -------------- | --- | --- | --- |
    | First call     |     |     |     |
    | Second call    |     |     |     |

## Part 2: Tracing

1. By hand, trace the following program. Show the intermediate values assigned to each variable in `main` and `display`, then write the program output.
   
   ```python
    def display(a,b):
        c = 2 * a + b
        print (a, b, c)
    
    def main():
        n = 3
        display(5, n)
        display(n, n)
        display(n * n, 12)

    main()
    ```

1. By hand, trace the following program. Show the intermediate values assigned to each variable in `main` and `silly`, then write the program output.

    ```python        
    def silly(a,b,c):
        c = a + b
        b = c
        a = 2.0 * a
        d = int(a + b + c)
        print(a, b, c, d)
        return d


    def main():
        a = 10
        b = 2
        c = 3
        d = 4
        print(a, b, c, d)
        d = silly(b, a, c)
        print(a, b, c, d)

    main()
    ```

1. By hand, trace the following program. Show the intermediate values assigned to each variable in `main` and `silly`, then write the program output.

    ```python
    PTS_PER_GOLD = 3
    PTS_PER_SILVER = 2
    PTS_PER_BRONZE = 1

    def gold_pts(g):
        g = g + 1
        return g * PTS_PER_GOLD

    def silver_pts(s):
        s = s - 1
        return s * PTS_PER_SILVER

    def bronze_pts(b):
        b = b
        return b * PTS_PER_BRONZE

    def total_pts(g,s,b):
        return gold_pts(g) + silver_pts(s) + bronze_pts(b)

    def run():
        g = 1
        s = 2
        b = 3
        print(g,s,b)
        tp = total_pts(g,s,b)
        print(tp,b,s,g)

    g = 3
    s = 1
    b = 2
    run()
    print(g,s,b)
    ```

## Part 3: Design 

1. Design a function to compute the annual rate of inflation. The function is passed two prices for the same item: the price one year ago and the price today. The inflation rate is returned as a floating point number (for example, 0.053 to mean 5.3%).
    
    1. Ensure you understand the problem.
    2. Develop an *algorithm* to solve the problem in pseudocode.
    3. Write the function definition.
    4. Write a short segment of code which illustrates how the function could be used to display the rate of inflation, given that a hot dog cost $0.75 last year and $1.25 today. Write the result to the user as a percentage.

2. By following a similar approach as above, design a function which, given three sides of a triangle $a$ $b$ and $c$, computes the area of the triangle. The area can be calculated using Heron's formula:
    
    $$A = \sqrt{s(s - a)(s - b)(s - c)}$$
    
    where $s$ is the semiperimeter of the triangle:
    
    $$s = \frac{a + b + c}{2}$$