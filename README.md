# ENGR 102 Lab Topic 4 (team)
This lab consists of four team activities. Please submit the following files to Gradescope. Please include the team header information at the top of each file with the names of all contributing team members. This is a team assignment, but **everyone** must submit the files for credit. You may discuss the problems with other teams, but your submitted work must be unique. Check out the [Frequently Asked Questions](#frequently-asked-questions) below.

## Activities

1. [Roundoff Error](#roundoff-error)
2. [Make Change](#make-change)
3. [Pretty Equation](#pretty-equation)
4. [Boolean Expressions](#boolean-expressions)

## Roundoff Error

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
