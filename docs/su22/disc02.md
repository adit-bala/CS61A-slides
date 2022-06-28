---
marp: true
theme: uncover
class: invert
style: |
    section {
        font-size: 180%;
    }
    footer {
        font-size: .6em;
    }
paginate: true
footer: "Slides by Aditya Balasubramanian"
---

<!-- 
_paginate: false
_footer: Slides available at [`teaching.aditbala.com`](https://teaching.aditbala.com)
_class: invert
-->

# <!--fit--> Discussion 02

### Environment Diagrams, Lambdas, Higher-Order Functions

Aditya Balasubramanian
`aditbala [at] berkeley [dot] edu`

---

<!-- 
_class: invert
_footer: 6/27
_backgroundColor: #2222
-->

# <!-- fit --> Announcements :mega:

- First Project (Hog) released !!!
    - Checkpoint due 7/1
    - Project due 7/6
    - Extra Credit (start early)
- First Homework released (HW01)
    - Getting started videos
    - Due Thursday (6/30)
- Quick note
    - 61a is 2x speed
    - Make sure to use resources
---
## Boolean Expressions Clarification

 *  `True and not False or not True and False`
 *  `(True and (not False)) or ((not True) and False)` -> `True`
 * `False or 1 and 4`
 * `False or (1 and 4)` -> `4`

---
<!-- 
_class: invert
_footer: 6/26/2022

-->

# Agenda :page_facing_up:

- Mini-Lecture on environment diagrams
- `Q1`, `Q2` (walkthrough)
- Mini-Lecture on `lambda`s
- `Q3`
- Mini-Lecture on `HOF`
- `Q4, Q5`





---
<!-- 
_class: invert
_backgroundColor: #2222
-->

# <!-- fit --> Environment Diagrams :earth_americas:

---

<!-- 
_class: invert
-->

## Enviroment Diagrams

* What are they?
    - A way to model how our program runs line by line
    - Keep track of variables, function calls and what they return, etc.
* Why use them?
    - Can help us understand where there is a bug in program (debugging)
    - Useful for other questions (WWPD, coding)
    - Exam points!

---

## Important Concepts

* Expressions
    - Evaluate to values
    - `1 + 1` -> `2`
* Statements
    - Bind **names** to **values**
    - **Names**
        - `def` statements, assignment statements, </br> variable names
    - **Values**
        - numbers, strings, functions, or other objects
    - `x = 2` 
    - doesn't return anything

---
## Frames

* What are they?
    - Frames list the bindings of variables and their corresponding value
* What are they used for?
    - Used to look up the value of a variable
* `Global Frame` always exists

---
<style scoped>
  pre > code {
    font-size: 170%;
  }
</style>

## Assignment Statements

- Assignment statements (denoted by =) creates new binding in frame
- Evaluate right side **completely** before binding to left side
- Example

```python
x = 11 % 4
y = x
x **= 2
```

![bg auto right:50%](https://i.imgur.com/olxuGij.jpg)

---
<style scoped>
  pre > code {
    font-size: 170%;
  }
</style>
## Def statements

* `def` statements are used to bind **function objects** to a **variable**
* Binding name is function name
* Parent of the function is frame where function is defined
* Keep track of *name*, *parameters*, *parent frame*
* Example
```python
x = 3
def square(x):
    return x ** 3
square(x)
```


---

## Def statements

- Only bind, **NO** execution until function is called
    - `def foo():` -> define function called `foo` with no parameters
    - `foo()` -> execute foo

![auto vertical](https://i.imgur.com/QFXAaeW.jpg)

---

<!-- 
_class: invert
style: |
    section {
        font-size: 170%;
    }
-->

## Call Expressions

* Syntax: `function_name(arg1, arg2, ...)`
* `sum(square(2), 2 + 2)`
* Create new frame for call expression
* Steps for evaluating:
    1. Evaluate operator (function)
        - See if it exists
            - `sum` adds two numbers
    2. Evaluate operands (args)
        - simplify args
            - `square(2)` -> `4`
            - `2 + 2` -> `4`
    3. Apply operator to the operands
        - `sum(4, 4) -> 8`

---

<!-- _class: invert -->

## Creating New Frames

* Give frame with unique index (`f1`, `f2`, `f3`)
* Label frame with name of function object
    - not always the variable name
* Label function's parent (frame in which it is defined in)
* Every function has return value
    - Return value can be `None`

 ---

<!-- _class: invert -->

 ## Variable Lookup

 * Start in current frame
 * If variable does not exist, search parent frame
 * If variable still does not exist, continue looking in parent frames
 * If variable does not exist, program errors

 ---

<!-- _class: invert -->

# Question 1 (5 minutes)

Let’s put it all together! Draw an environment diagram for the following code. You may not have to use all of the blanks provided to you.
<style scoped>
  pre > code {
    font-size: 170%;
  }
</style>

```python 
def double(x):
    return x * 2

hmmm = double
wow = double(3)
hmmm(wow)
```

---
<style scoped>
  pre > code {
    font-size: 170%;
  }
</style>

# Question 2 (walkthrough)
Draw the environment diagram that results from executing the code below. 
```python
def f(x):
    return x

def g(x, y):
    if x(y):
        return not y
    return y

x = 3
x = g(f, x)
f = g(f, 0)
```


 ---

 <!-- 
_class: invert
_backgroundColor: #2222
-->

# <!-- fit --> `lambda` Functions λ

---

 <!-- 
_class: invert
-->

## `lambda` Functions λ
* What are they?
    - A quicker and simpler way to define a function
    - Can also be used as the operator for a function
* Why use them?
    - Useful for scenarios in which you only want to use a function once and never again
* Syntax
    - written in 1 line
    - `lambda <args> : <body>`

---
 <!-- 
_class: invert
-->
<style scoped>
  pre > code {
    font-size: 170%;
  }
</style>

## `lambda` Function Examples Pt. 1

```python
def add_and_square(x, y, z):
    return (x + y + z) ** 2

lambda_add_and_square = lambda x, y, z : (x + y + z) ** 2
```

```python
def error():
    return 1 + 2 / 0

lambda_error = lambda : 1 + 2 / 0
```

---

<style scoped>
  pre > code {
    font-size: 170%;
  }
</style>

## `lambda` Examples Pt. 2

```python
>>> lambda x : x // 3

>>> (lambda x : x // 3)(5)

>>> wow = lambda x: lambda y: lambda z: x * y * z
>>> wow(3)(7)(5)

>>> (lambda x: x(3,4))(lambda a,b: a ** b)

```
---

<style scoped>
  pre > code {
    font-size: 170%;
  }
</style>

## `lambda` Examples Pt. 2

```python
>>> lambda x : x // 3
Function
>>> (lambda x : x // 3)(5)

>>> wow = lambda x: lambda y: lambda z: x * y * z
>>> wow(3)(7)(5)

>>> (lambda x: x(3,4))(lambda a,b: a ** b)

```

---

<style scoped>
  pre > code {
    font-size: 170%;
  }
</style>

## `lambda` Examples Pt. 2

```python
>>> lambda x : x // 3
Function
>>> (lambda x : x // 3)(5)
1
>>> wow = lambda x: lambda y: lambda z: x * y * z
>>> wow(3)(7)(5)
105
>>> (lambda x: x(3,4))(lambda a,b: a ** b)

```

---

<style scoped>
  pre > code {
    font-size: 170%;
  }
</style>

## `lambda` Examples Pt. 2

```python
>>> lambda x : x // 3
Function
>>> (lambda x : x // 3)(5)
1
>>> wow = lambda x: lambda y: lambda z: x * y * z
>>> wow(3)(7)(5)
105
>>> (lambda x: x(3,4))(lambda a,b: a ** b)
81
```
---

<style scoped>
  pre > code {
    font-size: 170%;
  }
</style>

## `lambda` Examples Pt. 2

```python
>>> lambda x : x // 3
Function
>>> (lambda x : x // 3)(5)
1
>>> wow = lambda x: lambda y: lambda z: x * y * z
>>> wow(3)(7)(5)
105
>>> (lambda x: x(3,4))(lambda a,b: a ** b)
81
```
---
<style scoped>
  pre > code {
    font-size: 170%;
  }
</style>

# Question 3 (10 minutes)

Draw the environment diagram for the following code and predict what Python will output.

```python
a = lambda x: x * 2 + 1
def b(b, x):
    return b(x + a(x))
x = 3
x = b(a, x)
```
---

<!-- 
_class: invert
_backgroundColor: #2222
-->

# <!-- fit --> Higher Order Functions :cloud: :partly_sunny: :cloud:

--- 

<!-- _class: invert -->

## Higher Order Functions (HOF)

* What are they?
    - Functions that either return functions as output or take in other functions as inputs
* Why use them?
    - When you want to use a function within another function
    - Treat them as an object
* Important Note
    - Let's see we have function `foo()` that takes in zero parameters
    - `foo` refers to the function object and is **NOT** calling the function
    - `foo()` shows that we are actually calling the function

---

<!-- _class: invert -->
<style scoped>
  pre > code {
    font-size: 200%;
  }
</style>

## HOF Function as Input Example

 ```python
>>> def exec_func(func, a):
        return func(a)

>>> exec_func(lambda x : x * 4, 4) 
16

>>> exec_func(lambda x : pow(x, 2), 2)
4

```

---

<!-- _class: invert -->
<style scoped>
  pre > code {
    font-size: 170%;
  }
</style>

## HOF Function as Output Example

```python
>>> def first(x):
        def square(y):
            def mod(z):
                return (x ** y) % z
            return h
        return g

>>> a = first(2)
>>> b = a(4)
>>> b(3)
```
---

<!-- _class: invert -->
<style scoped>
  pre > code {
    font-size: 170%;
  }
</style>

## HOF Function as Output Example

```python
>>> def first(x):
        def square(y):
            def mod(z):
                return (x ** y) % z
            return h
        return g

>>> a = first(2)
>>> b = a(4)
>>> b(3)
1
```

---
<style scoped>
  pre > code {
    font-size: 170%;
  }
</style>

# Question 4 (10 minutes)

Draw the environment diagram for the following code and predict what Python will output.

```python
n = 9
def make_adder(n):
    return lambda k: k + n
add_ten = make_adder(n+1)
result = add_ten(n)
```

---

<style scoped>
  pre > code {
    font-size: 150%;
  }
</style>

# Question 5 (10 min)

Write a function that takes in a number `n` and returns a function that can take in a single parameter `cond`. When we pass in some condition function `cond` into this returned function, it will print out numbers from 1 to `n` where calling cond on that number returns `True`.

```python 
def make_keeper(n):
    """Returns a function which takes one parameter cond and prints
    out all integers 1..i..n where calling cond(i) returns True.

    >>> def is_even(x):
    ...     # Even numbers have remainder 0 when divided by 2.
    ...     return x % 2 == 0
    >>> make_keeper(5)(is_even)
    2
    4
    """
```

---

<style scoped>
  pre > code {
    font-size: 145%;
  }
</style>

```python 
def make_keeper(n):
    """Returns a function which takes one parameter cond and prints
    out all integers 1..i..n where calling cond(i) returns True.

    >>> def is_even(x):
    ...     # Even numbers have remainder 0 when divided by 2.
    ...     return x % 2 == 0
    >>> make_keeper(5)(is_even)
    2
    4
    """
     def keeper(cond):
      i = 1
      while (i <= n):
        if cond(i):
          print(i)
        i += 1
    return keeper # remember this line
```
---

# Thank you!

### Attendance Form -> https://tinyurl.com/adit-disc02

### Anon Feedback -> https://tinyurl.com/adit-anon

### Study Groups -> https://tinyurl.com/adit-study