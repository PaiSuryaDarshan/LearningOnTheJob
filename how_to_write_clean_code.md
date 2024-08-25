# Writing clean code
REFERENCE: [How To Write Clean Code - Tech With Time](https://www.youtube.com/watch?v=F14BKKHeAKU)

### 1. Stay consistent with Snake_case for python

Snake_case = this_is_snake_case
camelCase = thisIsCamelCase ---> More common for JavaScript (not python though)

### 2. when a variable holds a constant value through out the code, It should be labelled with ALL CAPS

for example, when width of screen is constant from the time the program is opened.

The incorrect way to label the "width" variable:

    wScreen  = 1200
    width    = 1200 
    w_screen = 1200

The correct way to label the "width" variable

    WIDTH = 1200

This is because the variable does NOT change throughout the use of the program.

### 3. class names in python have a unique convention
They must follow the "pascal case" convention

Snake case: (INCORRECT convention)

    my_new_class

camel case: (INCORRECT convention)

    myNewClass

Pascal case: (***CORRECT convention***)

    MyNewClass

Notice the caps on the first word (unlike that in camel case)

### 4. Add a space after comma 
    Wrong:      (a,b,c,d,e,f)
    correct:    (a, b, c, d, e, f)

### 5. Don't use brackets the return format after a function

Incorrect:

    def new_function(A):
        return (B,C)
Correct:

    def new_function(A):
        return B,C
    
    # This is because in python, when a functions returns multiple values,
    # it is already formatted as a Tuple.

### 6. Write self-commenting code, be as clear as possible

Let's take the example of a function that returns the color "Snuff" with colour code (227, 218, 231, 1) in the RGBA format (from [this website](https://www.flatuicolorpicker.com/magenta-rgba-color-model/#))

Incorrect:

    1.    color.show(227, 218, 231, 1)
        # No way of knowing what the color is. 

    2.  color_used = (227, 218, 231, 1)  
        color.show(color_used)
        # Still, No way of knowing what the color is 

    3.  snuff = (227, 218, 231, 1)  
        color.show(snuff)
        # Wrong formatting for a constant variable 

VERY ANNOYING to deal with, ESPECIALLY when you return to an old piece of code that you are trying to fix and now have to figure out what the 
RGBA format translates to

Correct:

    SNUFF = (227, 218, 231, 1)  
    color.show(SNUFF)
    
    # Use ALLCAPS for representing a variable that
    # remains constant throughout 

This is the standard way of tagging such code... This is also what is meant by, "writing self documenting (or self commenting) code".

### 7. Avoid using try and except loops when you are not trying to catch a specific exception

INCORRECT:

    try:
        result = A+B/C
    except:
        result = "IDK"

In these cases, try your best to use If/Else statements.

CORRECT:

    try:
        result = A+B/C
    except IndexError:      
        # trying to catach one specific type of errot
        result = "C is 0"

### 8. Break down lists/Tuples to individual variables

INCORRECT:
    
    list_of_parameters = [VAR_Mouse_postion_X, VAR_Mouse_postion_X]

    def mouse_reader(list_of_parameters[0], list_of_parameters[1]):
        return result
    
CORRECT:

    list_of_parameters = [VAR_Mouse_postion_X, VAR_Mouse_postion_X]

    mouse_x = list_of_parameters[0]
    mouse_y = list_of_parameters[1]

    def mouse_reader(mouse_x, mouse_y):
        return result

Another CORRECT Method: (Tuple Decomposition) [Best Technique - Senior lvl]

    list_of_parameters = [VAR_Mouse_postion_X, VAR_Mouse_postion_X]

    # Tuple Decomposition - auto-decodes the variables
    mouse_x, mouse_y = list_of_parameters

    def mouse_reader(mouse_x, mouse_y):
        return result

TA-DAAAA! Self-commenting code :D.

### 9. Skip one line between 2 functions, but skip TWO after a class
    
    class MyClass:
        aasd
        sadf
        sadf
        sdaf
                                                            <->
                                                            <->
    def func_1():
    return result_1
                                                            <->
    def func_2():
    return result_2
                                                            <->
    def func_3():
    return result_3

NOTICE the 2 spaces between the class and function. BUT only one space between func and func. This is just good practice and a standard Python convention.

### 10. Add comments to categorise variables

    # Screen Size
    WIDTH = 1200
    HEIGHT = 1080

    # Colors
    SNUFF = (227, 218, 231, 1) 
    BLACK = (0, 0, 0, 1) 
    WHITE = (255, 255, 255, 1) 

Good practices for code descriptive comments (for organising)

### 11. Learn to get effective with things like "break", "continue, "pass" etc.

### 12. Define ALL constant variable at the VERY TOP of your program (under the import preamble)

    import x
    import y
    import z

    # Colors
    SNUFF = (227, 218, 231, 1) 
    BLACK = (0, 0, 0, 1) 
    WHITE = (255, 255, 255, 1) 

    #Other Constants
    (etc.)


This is standard and just makes code more readable and convenient.

### 13. [MOST IMPORTANT] Try your best to avoid multiple indentation levels. AVOID NESTING AS MUCH AS POSSIBLE

INCORRECT:

    if this:
        if this:
            if this:
                if this:
                    do this

CORRECT:

    if not this:
        continue (or break)
    if not this:
        continue (or break)
    if not this:
        continue (or break)
    if not this:
        continue (or break)
    
        do this

This key to making code (especially long ones) look more attractive.

This takes a while to master but definitely DO IMPLEMENT THIS!

### 14. Be CONSISTENT with your choices
It's fine to choose camel or pascal case BUT BE CONSISTENT with it through out your code.
