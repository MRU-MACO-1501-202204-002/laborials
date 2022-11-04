# Laborial-16

**Topic: Even MORE Loop Practice...will the madness never end?!?**

## Instructions

The following exercises will give you further practice writing loops. 

## Exercises

1. The "factorial" of an integer is the product of that integer and all the integers less than it. It is denoted with an exclamation mark (!). So,

    n! = n * (n-1) * (n-2) * ... * 2 * 1
    
    Write a function called `factorial` that computes the factorial of a given integer using a while loop. 

    ```python
    # example use
    factorial(0)  # should return 1
    factorial(1)  # should return 1
    factorial(2)  # should return 2
    factorial(3)  # should return 6...
    ```

2. Imagine you are creating an online service, and are writing the code that handles creation of user accounts. 
You must write write two Python functions to help you with your job:

    1. The first function should be called `invalid_password`. It takes in a string and returns true if that string is an **invalid password**, and false otherwise. A password is considered invalid if it has fewer that 8 characters or is one of these poor password choices:
         - "password"  (case sensitive)
         - "12345678"


        ```python
        # example use
        invalid_password("h1")           # should return True; too short!
        invalid_password("12345678")     # should return True; poor choice
        invalid_password("PASSWORD")     # should return False; not exactly "password"
        invalid_password("w00tw00tWOO!") # should return False; everything OK!
        ```

    1. The second function should be called `valid_password_from_user`. It should prompt the user for a password and validate that password using a while loop and the `invalid_password` function. It should return the validated password.


    Once you think you have these functions working, use this `main()` to test them:

    ```python
    def main():
        validated_password = valid_password_from_user()
        print(validated_password, "is a valid password.")
    ```

    Here is an example run of a working final result:
   
    > choose a password: **1234**  
    > Oops - password must be at least 8 characters long and not 'password' or '12345678'!   
    > choose a password: **password**  
    > Oops - password must be at least 8 characters long and not 'password' or '12345678'!  
    > choose a password: **password1234**  
    > password1234 is a valid password.  
        
