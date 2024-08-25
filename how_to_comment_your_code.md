# Writing Comments
REFERENCE: [Documenting Python Code: A Complete Guide](https://realpython.com/lessons/documenting-vs-commenting-code/)

## Why Comment?

    Code tells you "How?" Comments tell you "Why?" 
                 ~ Jeff Atwood (a.k.a.Coding Horror)

1. It describes code for fellow developers
2. Aids maintenance and further development of code
3. Guides the reader to better understand the code, it's purpose and it's design.

## Types/Variations of Comments

1.  ***Comments for Planning and Reviewing code*** (*PNR*)
    Theses comments are usually deleted after the plan is complete.
    e.g. 
    #First Step

2.  ***Code description comments***
    It explains the intent of a specific section of code.
    e.g. 
    #Accepts request if condition XYZ is met, if unsuccessful,
    #returns exception "ABC"

3.  ***Algorithmic description comments***
    It explains the reason Technique/path 'X' was chosen over 'Y'.
    e.g. 
    #Using 'quick sort' for performance gains

4.  ***Tagging comments***
    It marks bugs / broken code, for review later. Theses comments must be deleted after the issue is resolved.
    Common examples include,
    #BUG: Cause crash when run with XYZ 
    #FIXME: Not very efficient code. Revisit and improve
    #TODO: Add condition for when 'Val' is NaN

## Essential Rules to follow when Commenting

As a rule of thumb, A comment should not be longer than 72 characters, if it is longer than 72, then split it up over multiple lines.

There are additional 4 major rules of thumb to follow (as suggested by *Jeff Atwood*):
1. ***Keep Comments as close as possible to the code they describe.***
    Keep it exactly to what the code does, not where its from or what the out put is going to be used for later. This will keep it short and simple, which will be relatively less frustrating to the reader

2. ***Don't use complex formatting such as tables and ASCII figures.***

3. ***Don't include redundant information.***
    Assume the reader (usually yourself) already has a good base understanding of python (or whichever language)

4. ***Design your code to be as self explanatory as possible. Design your code to comment itself.***
    This is where type hinting comes in handy. You can avoid a huge chunk of comments if this is done well.