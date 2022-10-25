# Laborial-11

**TOPIC: Debugging, Testing, and Refactoring**

This tutorial gives you a chance to read some physics formulas, debug some code, make some functions, and generally have an absolutely _wonderful_ time.

## Introduction

Imagine your company is developing a turn-based tank battle game (like the classic [Scorched Earth](https://en.wikipedia.org/wiki/Scorched_Earth_(video_game)) game). Players take turns selecting a **launch angle** and **velocity** to launch a projectile at the other player, and the first to hit their opponent wins.

Unfortunately (well, for _you_), your co-worker has just won the lottery and quit, leaving you with some half-finished code. They have written a function to compute how far a projectile will travel given a launch angle and velocity, but the code hasn't been tested yet and will likely need to be debugged. 

## A Bit of Useful Physics You'll Need

Projectile kinematics (a.k.a. the science of lobbing s**t at far-away places) says that for a projectile launched on a flat surface, the flight-time (the time the projectile is in the air until it lands) satisfies the quadratic equation:

> ½ *g t*<sup>2</sup> + *v* sin(*a*) *t* = 0
>  
> where,  <br>
> *t* is the **flight time** in seconds <br>
> *a* is the **angle of launch**  <br>
> *v* is the **velocity of launch** in **m/s**  <br>
> *g* is the **acceleration due to gravity** (9.81 m/s<sup>2</sup> on earth) 

Given velocity *v* and angle *a*, this equation can be solved for *t* using the [quadratic formula](https://en.wikipedia.org/wiki/Quadratic_formula).

Once you've calculated a value for the flight time (t), you can find the horizontal distance travelled during that time with another formula:

> *x* = *v* cos(*a*) *t*
> 
> where,  <br>
> *x* is the **horizontal distance** travelled  <br>
> *v* is the **velocity of launch** in m/s  <br>
> *a* is the **angle of launch**  <br>
> *t* is the **flight time** in seconds

## What Your Co-Worker Left You

Your (ex)co-worker, who was no fool, did some math on paper, and identified 3 trajectories (shown below) that would cause the projectile to travel 500 m.

_Note: The 80° and 65° trajectories don't exactly hit the 500 m mark - but they are "good enough"!_

![trajectories](images/trajectories.png)

*Figure 1: Three sample trajectories that will cause a projectile to travel 500 m*

Your co-worker then made a function to compute the horizontal distance travelled by a projectile. The intent of the function is to accept a launch angle and velocity as parameters, use the [quadratic formula](https://en.wikipedia.org/wiki/Quadratic_formula) to compute *t*, and then use *t* to compute (and return) *x* using the equation above.

Being no fool, they also created some code to test their distance function...but then they hit it big and bailed on you.

```python
# gives access to cos, sin, and sqrt (square-root) functions
from math import cos, sin, sqrt  

# gravitational acceleration = 32.2 ft/s/s
g = 32.2 


def calculate_landing_point(angle: float, velocity: float) -> float:
    """
    Compute the horizontal distance the projectile will travel

    :param angle: launch angle from horizontal, in degrees
    :param velocity: velocity in meters / second
    :return: distance travelled in meters
    """

    # solve quadratic formula for positive t, the flight time
    a = -0.5 * g
    b = velocity * sin(angle)
    c = 0
    t = (-b - sqrt(b ** 2 - 4 * a * c) / a * 2

    # calculate the horizontal distance travelled during time t
    x = v * cos(angle) * t

    return x

def test_with(angle: float, velocity: float) -> None:
    """
    See whether calculate_landing_point returns
    a value close enough to an expected distance.

    :param angle: launch angle for scenario, in degrees
    :param velocity: velocity for scenario, in m/s
    """
    EXPECTED_DISTANCE = 500
    ACCEPTABLE_ERROR = 3.0

    actual_distance = calculate_landing_point(angle, velocity)

    difference = abs(EXPECTED_DISTANCE - actual_distance)

    assert difference < ACCEPTABLE_ERROR, f'the calculated distance, {actual_distance:.1f} m, is not close enough to 500 m'



def test_scenarios() -> None:
    """
    Use known working scenarios to test calculate_landing_point
    """
    test_with(80, 120)


test_scenarios()
```




## What You Need to Do

### Part 1: Get the code into VS Code & clean up syntax errors

1. Paste the code above into VS Code.
2. Does VS Code seem unhappy about anything? Then make it happy.
   - You should understand **why** it's complaining...if you don't, that's something you'll need to add to your "to study" list.
   - There are **3 syntax errors** you'll need to fix.

### Part 2: Read the code to find the first logic error

1. Take a few moments to actually **read** the code. 
    - Is there anything that seems confusing? If so, ask for help.
    - Does the code use the [physics formulas mentioned earlier](#a-bit-of-useful-physics-youll-need)? Where?
    - Does anything seem...off? If you've actually read through the physics blurb, you _should_ be able to spot a logic error in the code without even running the code! If you've spotted the issue, fix it; otherwise, ask for a hint -then fix it.

> _With a bit of experience - and sometimes just plain luck - you can spot errors visually simply by skimming through code. Consider yourself fortunate if this is the case, but if not, just soldier on!_

### Part 3: Track down the remaining logic errors

1. Run the code. 
   - What function is being called when you do that? 
   - Do you understand what that function is doing? If you don't, stop and find out.
   
> There are **3 logic errors** in the code. You should have spotted one of them in Step 2. Unless you managed to spot the remaining two visually in Part 2, you now have some detective work to do! Time to start working backwards:

1. What don't you like about what is showing up in the terminal? 
2. What line of code prints that thing you don't like?
3. What line of code assigns a value to the variable that has the incorrect value?
4. What function is providing that wrong value?
5. Where does that function return the wrong value?
6. Where is that wrong value calculated? And what does that mean about the variables involved in that calculation?
7. How can you confirm that those variables are what you think they are? AND WHAT DO YOU THINK THEY ARE?

Continue working backward like this until you find the 2 logical errors. Ask for some hints if you get stuck.

### Part 4: Improve the code

A good habit to get into is to **improve code that's working**. This process is known as **refactoring**. (You don't need to remember that term...but it _is_ a common term in industry, so knowing it makes you look cool.)

Let's do a little refactoring!

1. You only have one of the 3 known sample trajectories in `test_scenarios`. Add the other 2 - and make sure those tests still pass!
2. The quadratic formula used to calculate `t` in our program has `c = 0`, which means that formula simplifies quite a bit. Why don't you simplify the t calculation - and then make sure those tests still pass!
3. The `calculate_landing_point` function is doing quite a bit of work - it's both calculating the flight time AND using a flight time to calculate a distance. We should create 2 functions that do those 2 things and have `calculate_landing_point` call those functions.
   1. Define a new function with a reasonable name that calculates the flight time. What parameters should it have?
   2. Paste the code from `calculate_landing_point` into this new function's body.
   3. Call this new function from `calculate_landing_point` and store the value in `t`.
   4. Run the program to test that you haven't busted anything.
   5. Now do something similar to create and call a new function that calculates the distance travelled from `t`.
   6. Run the program to test that you haven't busted anything.

---

Which of these debugging techniques did you use to find the bugs?
    - [ ] visual inspection
    - [ ] letting the IDE highlight syntax errors
    - [ ] checking whether code implements the intended functionality
    - [ ] manual code tracing
    - [ ] commenting out some lines of code to simplify the program
    - [ ] adding `print` statements to print out intermediate results for inspection
    - [ ] using breakpoints and IDE debugger to step through the code
    - [ ] calling a function with test inputs to check its functionality
    - [ ] anything else not on this list?
