# ENGR 102 Lab Topic 4 (team)
This lab consists of four team activities. Please submit the following files to Gradescope. Please include the team header information at the top of each file with the names of all contributing team members. This is a team assignment, but **everyone** must submit the files for credit. You may discuss the problems with other teams, but your submitted work must be unique. Check out the [Frequently Asked Questions](#frequently-asked-questions) below.

## Activities

1. [Roundoff Error](#roundoff-error)
2. [Make Change](#make-change)
3. [Pretty Equation](#pretty-equation)
4. [Boolean Expressions](#boolean-expressions)

## Roundoff Error
When performing numerical computations, one of the challenges you can run into is floating-point roundoff error. This occurs when the computer needs to represent a number that would require an infinite number of decimal digits, but rounds them off after some point. That small roundoff error can cause some significant issues. This activity is meant to help you understand floating-point roundoff error a bit more and learn about one way of dealing with it. Create a Python file named `roundoff_error.py` for the following three-part activity. Please separate the various parts of your code with the following comment identifying the separate sections (copy/paste into your file with the appropriate letter).
```
############ Part A ############
```

### Part A: Identifying floating-point problems
First, **type** and run the following program:

![I SAID TYPE, NOT COPY/PASTE! NEVER COPY/PASTE CODE YOU DIDN’T WRITE. ESPECIALLY NOT FROM THE INTERNET!](roundoff_error_part_A_1.png)

Notice that the value of `a` is rounded off. The value of `b`, if we have no roundoff, should be `1`. Is it? *Make a comment in your code answering the question.*

Now add the following lines:

![DID YOU TRY TO COPY/PASTE AGAIN? TYPE THE CODE! DON’T BE LAZY!](roundoff_error_part_A_2.png)

In this case, the value of `f`, if we have no roundoff, should be `1`. Is it? *Make a comment in your code answering the question.*

Finally, add the following lines:

![STILL TRYING TO COPY/PASTE? THIS IS GOOD PRACTICE FOR TYPING! YOU’LL REMEMBER IT BETTER IF YOU TYPE INSTEAD OF COPY/PASTE!](roundoff_error_part_A_3.png)

Again, the values of `y` and `z`, if we have no roundoff error, should be `1` in both cases. Are the values 1? *Make a comment in your code answering the question.*

Was that surprising? You should have seen from those examples that sometimes we will encounter issues due to roundoff error and sometimes we won’t. We can’t always predict when roundoff error will be obvious.

### Part B: Tolerances for Comparisons
In Part A, you should have seen that two different ways of computing values that should be identical might actually produce values that are different, if only by a tiny bit. In some cases, this is not a problem. For example, we usually don’t care if speed is incorrect in the 10<sup>th</sup> decimal place, since we usually can’t measure speed that precisely anyway. But, floating point error can become a big problem if comparisons are made with floating-point values.  

A common way for dealing with floating-point error is to use tolerances. Tolerances let you compare two values that are close, but not identical to each other. Rather than checking whether or not `a == b`, we instead compute the absolute value of the difference in `a` and `b` and see if that quantity (the difference) is within some small distance away from `0` (either above or below). That small value, called the tolerance, is decided upon by the programmer and the value chosen is highly dependent on the problem at hand. If the absolute value of the difference between `a` and `b` is less than the tolerance, then we may consider `a` and `b` to be equal for the problem at hand. The tolerance is commonly abbreviated `TOL` or `EPS` (short for epsilon (`ε`)). `1e-6` is usually a good value for tolerance, but may vary with specific applications.

Add to your code from Part A the following lines to compare values of the variables `b` and `f` using the concept of tolerance:

![WHEN YOU COPY/PASTE, ‘ MAY BE WRITTEN FUNNY. YET ANOTHER REASON TO TYPE THE CODE!](roundoff_error_part_B.png)

Add a similar tolerance check to your code for `y` and `z`. 

As you write programs, think about your comparisons and decide if you need to use tolerances. If you are making a comparison to check for exact equality and you might have some floating-point error, you will probably want to use tolerances, while if you are just checking which of two things is larger, a tolerance comparison is likely unnecessary. Tolerances are particularly helpful when checking things like whether a denominator is (nearly) 0, and thus a division is likely to create error.

### Part C: Illusions of Precision
Computers operate in base 2 (binary). No matter how many digits you are willing to use, some numbers still cannot be represented exactly, like the number 0.1. Most people aren't aware that 0.1 is stored as an approximation because Python keeps the number of digits manageable by displaying a rounded value. Even though the printed result of a calculation may look exact, know that the actual stored value is the nearest representable binary fraction.

Add to your code from Part B the following lines:

![AGGIES DO NOT LIE, CHEAT, OR STEAL, OR TOLERATE THOSE WHO DO. BE AN AGGIE, ALWAYS WRITE YOUR OWN CODE!](roundoff_error_part_C.png)

Did the results surprise you? If you rewrote your program for [Lab Topic 1 Activity 3](https://github.com/tamu-edu-students/engr-102-lab-1?tab=readme-ov-file#follow-directions) using variables and successive divisions for `x` (`x = 1/10`, `x = 1/100`, etc) would you expect to see the same output as your original program? Check out this link to the Python documentation: https://docs.python.org/3/tutorial/floatingpoint.html. This info helps explain these issues. As the document states, ". . .this is not a bug in Python, and it is not a bug in your code either." Instead, the problems stem from the way a floating-point number is represented by the hardware. **Awareness of these issues may save you a lot debugging effort in the future.** Also check out this link: Binary Tutorial - 5. Binary Fractions and Floating Point https://ryanstutorials.net/binary-tutorial/binary-floating-point.php



## Make Change

## Pretty Equation

## Boolean Expressions

## Frequently Asked Questions
1. **Activity 2 (make change) do I have to manually check all possible cases?** Do you have to? No. *Should* you? Yes! How do you know your code works if you don't test it thoroughly? Of course if you're lazy you can just submit to Gradescope and see if it passes all of my tests. :)

2. **Activity 3 (pretty equation) how do I separate the minus sign from a negative number?** Get clever! This is a great time to use an if statement. If the number is negative, use string concatenation to display a minus sign, space, and the number times -1 (to flip the sign). The absolute value function may also be useful: `abs(number)`.

3. **Activity 3 (pretty equation) I am frustrated. Why is this problem so hard?** Well, I thought this problem would be a fun challenge, but you're right, it is hard. You will need several `if-elif-else` statements and will likely need to nest some of them. If you're struggling, ask for help during class!

4. **Activity 3 (pretty equation) I tried using backspace (`\b`) and Gradescope labels it `\x08` instead. What's going on?** Gradescope displays the `\b` character as `\x08`. To get around using `\b`, try building up your equation string one piece at a time using string concatenation. For example:
```python
a = 1
b = 2
c = -5
myeq = "x^2"
myeq += " + " + str(b) + "x"
myeq += " - " + str(abs(c)) + " = 0"
print(myeq)
```
5. **Activity 4 (Boolean expressions) I can't use `if-elif-else` blocks?!** Nope! You don't need `if-elif-else` blocks for this activity. Instead, use Boolean expressions. You know, something like `a and not b` which evaluates to a Boolean value. Try saying it out loud (in English) then translate to Python. 

6. **Activity 4 (Boolean expressions) the comment test case is failing but I commented my code. What gives?** Did you include the comment to separate sections of your code? Make sure you have the right number of `#`'s on that line.

Have a question you don't see here? Email your instructor!

Based upon Dr. Keyser’s Original<br/>
Revised Summer 2025 SNR
