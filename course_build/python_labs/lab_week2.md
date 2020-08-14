---
jupytext:
  formats: ipynb,md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: '0.9'
    jupytext_version: 1.5.1
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# Lab Week 2

+++

## Overview

The purpose of this lab is to get comfortable interacting with *Jupyter Notebooks* and learning a few useful things with Python. 

Nothing will be graded this week, but there are still submissions due in section 10 to gain familiarity with submitting code via *Canvas*. Students who have prior experience programming with notebooks may find some parts of this lab trivial, but we will be building much further on the concepts outlined here. 

+++

## Pair Programming

During labs you will be working in pairs using a technique called PAIR PROGRAMMING. It works like this:

* You pair up with someone else

* One person (the “driver”) sits in front of the computer and types. The other (the “navigator”) watches what is going on and makes comments.

* Every 15 minutes, you SWITCH roles (we will announce the switchover time).

* You are EACH responsible for handing in your own lab (you may or may not have identical labs). You MUST add a comment to the code with the name of your partner.

* If you have not completed the lab at the end of the lab period (which is usually the case), you are free to a) schedule more pair-progamming time with your partner, or b) complete the lab by yourself.


+++

## Goals

* Familiarize yourself with *Jupyter Notebooks* and write some code
  * Open a notebook
  * Make a folder (directory), open and save files to that directory

* Learn (by example) how to do a number of things which will become useful later on, such as
  * Load and save data from/to a ```.csv``` file
  * Initialize and use variables
  * Make x-y plots of data: play with colour, symbols, parts of your data set
  * Comment your code
  * Use the built in ```help()``` function to understand code, look up documentation 

+++

## Opening a Jupyter Notebook

Congratulations! If you are reading this you have successfully opened a Jupyter Notebook. 

### Relevant reading: 
* Kazarinoff 02.01
* Kazarinoff 02.02
* Kazarinoff 02.05

Im skipping this section for now, as I am unsure exactly how students will be accessing jupyter notebooks.

```{code-cell} ipython3
# this is a code cell
print("this is the output of the code cell")
```

### and 
* this
    * is *a* **markdown** ***cell***

+++

## Running Code

### Relevant reading 

* Kazarinoff 3.01, 3.02, 3.04
* HTTLACS "the way of the program" -first half

All computer programs (Python, or any other programming language) follow the principle of **input $\rightarrow$ process $\rightarrow$ output**. Lines of code are entered into the computer (in our case, we type *Python* code into a *Jupyter Notebook cell*), the machine *processes* the code (input is translated into *machine code* (binary 0's and 1's) by a *Python Interpreter*, which is then then run by your computer's CPU), and the output of the code is either displayed to the screen or saved somewhere in computer memory (for us, it appears in an output cell directly below the input). 

Let's see this in practice. The simplest program we can write is called "hello world" and it is a long-standing tradition that aspiring computer and data scientists write one as their first program. In Python, it looks like this:

```python
print("Hello World.")
```

Try it out for yourself. Input the line of code into the code cell below and press ```shift + enter``` to execute it (make sure your cursor is blinking inside cell). The output of your code will appear below the code cell. (You could also copy and paste the line above into the cell, which could be useful for longer bits of code)

```{code-cell} ipython3
# create your hello world program here, press shift + enter to execute
```

Congratulations on writing your first program! We inputted a line of code, processed it via the python interpreter and printed some output to the screen. In Python, ```print``` is a *reserved word*, which means that word in particular it has special meaning to the python interpreter. Specifically, it python interprets it to mean "output whatever is inside the brackets ```()``` to the screen." Try editing the code above to print your own message instead of "hello world."

>**Tip:** There are multiple ways to execute code in a notebook. You can click the $\blacktriangleright |$ **Run** button on the toolbar above, press ```shift + enter``` to run the current cell, or ```alt + enter``` to run the cell *and* create a new blank cell below the current one. The $\blacktriangleright\blacktriangleright$ button will run all the cells in your notebook from top to bottom. If your cell is having problems running (perhaps because of an error in the code), you can stop it by pressing $\blacksquare$ to edit your code and try running the cell again. 

+++

## Python as a Calculator

We can do more interesting things than output words to the screen. Python can also interpret numbers and symbols to do some basic math. Later, we will use it for some not-so-basic math as well. Just like the word ```print```, the Python interpreter assigns meaning to digits ```0 1 2 3 4 5 6 7 8 9```, and the mathemetical operators ```+ - * /```, and can solve algebraic expressions. The following cell outputs an answer to a simple math problem. Try editing the cell to solve another math problem of your choice, and verify the answer with a calculator or mental math.

```{code-cell} ipython3
14 + 9 / 2
```

Notice that Python preserves *order of operations* (brackets, exponents, division, multiplication, addition, subtraction, or BEDMAS), i.e. it gives the correct answer for $14 + \frac{9}{2} = 18.5$ instead of $\frac{14 + 9}{2} = 11.5$. 

+++

## Assigning Variables

For solving more complex problems, it is often a good idea to assign numbers to *variables,* and then perform mathematical operations on the variables instead of strictly numerical math. This helps keep everything organized, and lends some meaning to the problem being solved. This way, we can also re-use bits of the same code to solve multiple problems. Variable assignment in Python looks like this:




```{code-cell} ipython3
var = 16
```

which creates a variable called ```var``` and assigns the value of 16 to it. When programming, the ```=``` sign is called the *assignment operator*, and takes on a significantly different meaning than we are perhaps used to. The ```=```sign does **not** mean "```var``` and the number 16 are mathematically equivalent." Rather, it tells the interpreter: "locate some space in computer memory, save the number 16 there, and refer to that space by the name ```var```. Notice this cell does not produce any output, it 

+++

### Naming Conventions

Variable names must conform to the following rules in order to be recognized by Python:

   * variable names must start with a letter
   * variable names can only contain letters, numbers, and the underscore character ```_```
   * variable names can not contain spaces
   * variable names can not include punctuation
   * variable names are not enclosed in quotes or brackets
    


The following code lines show *valid* variable names:

```python
constant = 4

new_variable = 2

my2rules = 19

SQUARES = 4
```

The following code lines show *invalid* variable names:

```python
a constant = 4

3newVariables = [1, 2, 3]

&sum = 4 + 4
```

```borrowed/slightly modified from kazarinoff 3.02```

Additionally, there are a few style recommendations that most Python programmers follow. Variable names that violate these conventions will still be read by the interpreter, but may be confusing to other programmers (or you in the future).

   * variable names should make it easy to understand what they represent
   * variable names should consist of lower-case letters, with words separated by the ```_``` character (this is called "snake case")
   * variable names should be as succinct as possible
   

+++

Say we would like to calculate the circumference of the earth. We know that earth's radius is 6371km, and that the circumference of a circle (assume earth is perfectly round) can be calculated by

$$
C = 2\pi\cdot r
$$


```{code-cell} ipython3
radius = 
pi = 3.14159
```

```{code-cell} ipython3

```
