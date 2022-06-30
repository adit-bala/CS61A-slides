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

# <!--fit--> Discussion 03

### Recursion, Tree Recursion :)

Aditya Balasubramanian
`aditbala [at] berkeley [dot] edu`

---

<!-- 
_class: invert
_footer: 6/30
_backgroundColor: #2222
-->

##  Announcements :mega:

- Homework 1 due today (6/30)
- Lab 2 due today (6/30)
- Hog Checkpoint due tommorow (7/1)
- The tuition refund deadline to drop any session C summer course is July 1st.
    - There's also still lots of room in CS 10, if you're looking for a different pace than 61A—you can enroll in the class, and then reach out to cs10@berkeley.edu and they'll help catch you up.


---

## Agenda

- Mini Lecture - Recursion
- `Q2` walkthrough
- `Q1`
- `Q3`/`Q4`/`Q5`
- Mini Lecture - Tree Recursion
- `Q7`
- `Q8`


---

<!-- 
_backgroundColor: #2222
-->

# <!-- fit --> Recursion :dolls:

---

## Recursion

* What is a recursive function?
    - A function that calls itself
    - Returns a function call of itself, not the object (different than HOF)
* Recursive Leap of Faith
    - The idea that the recursive function will work no matter what/how many test cases are passed in

---

## Example

* The Problem
    - Want to find how many dolls are inside this doll
* What we need to do
    - Create a function that we can repeat until there is no more dolls to count
* Ideas?

![bg right](https://media.giphy.com/media/X8HbeXDF7nzaM/giphy.gif)

---

## Solution

- Remove one layer at a time and one to total, stop when there is no more dolls and add one

---

## Solution in Formal Terms of Recursion

* Base Case
    * smallest problem with guranteed answer, or smallest input
    * **A doll with no other dolls inside of it**
* Recursive Call
    * A method of reducing the current problem into a smaller problem
    * **Removing each layer one by one and adding it to a total**
* Using everything together
    * **Function:** (Add 1 to total and remove layer)
    **Base Case:** Stop once you you get to the smallest doll

---

# Recursion vs Iteration

* Recursion
    - Make problem smaller
    - Variables get reset
    - Many frames will open
        - Lot of memory taken up
    - Better for some problems
        - Recursive Data Structures (Trees, Linked Lists)
* Iteration
    - Loops happen in one frame
    - Easy to visualize
    - No additional function calls

---
<style scoped>
  pre > code {
    font-size: 170%;
  }
</style>

# Q2: Recursion Environment Diagram
Draw an environment diagram for the following code:
```python
def rec(x, y):
    if y > 0:
        return x * rec(x, y - 1)
    return 1

rec(3, 2)
```

---

<style scoped>
  pre > code {
    font-size: 170%;
  }
</style>

# Q1: Recursive Multiplication (7 min)
Write a function that takes two numbers m and n (only positive) and returns their product. Use recursion, not `mul` or `*`

```python
def multiply(m, n):
    """ Takes two positive integers and returns 
    their product using recursion.
    >>> multiply(5, 3)
    15
    """
    "*** YOUR CODE HERE ***"
```

---
<style scoped>
  pre > code {
    font-size: 150%;
  }
</style>

# Q3: Find the Bug
Find the bug with this recursive function.

```python
def skip_mul(n):
    """Return the product of n * (n - 2) * (n - 4) * ...
    >>> skip_mul(5) # 5 * 3 * 1
    15
    >>> skip_mul(8) # 8 * 6 * 4 * 2
    384
    """
    if n == 2:
        return 2
    else:
        return n * skip_mul(n - 2)
```

---
# Choose your own adventure !!!
## `Q3`, `Q4`, `Q5`
---
<!-- 
_backgroundColor: #2222
-->

# <!-- fit --> Tree Recursion :deciduous_tree:

---

## Tree Recursion :deciduous_tree:

* What is Tree Recursion?
    - Recursion, but more!
    - Multiple recursive calls
* When do we use them?
    - When we need to break problem down in more than one way
    - When we have multiple choices

---
<style scoped>
  pre > code {
    font-size: 145%;
  }
</style>

# Recursive Fibonacci
```python
def fib(n):
  if n == 0:
    return 0
  elif n == 1:
    return 1
  else:
    return fib(n - 1) + fib(n - 2)
```

* Need to look at `fib(n - 1)` and `fib(n-1)`
* All steps of recursion present
    - Base Case
    - Recursive Calls
    - Applying to solve problem

---
<style scoped>
  pre > code {
    font-size: 145%;
  }
</style>

# Q7: Count Stair Ways

How many different ways are there to go up a flight of stairs with `n = 1` step? How about `n = 2` steps? Try writing out some other examples and see if you notice any patterns.

```python
def count_stair_ways(n):
    """Returns the number of ways to climb up a flight of
    n stairs, moving either 1 step or 2 steps at a time.
    >>> count_stair_ways(4)
    5
    """
    "*** YOUR CODE HERE ***"
```
---

<style scoped>
  pre > code {
    font-size: 130%;
  }
</style>

# Q8: Count K
Consider a special version of the `count_stair_ways` problem, where instead of taking `1` or `2` steps, we are able to take up to and including `k` steps at a time. Write a function `count_k` that figures out the number of paths for this scenario. Assume `n` and `k` are positive.

```python
def count_k(n, k):
    """
    >>> count_k(3, 3) # 3, 2 + 1, 1 + 2, 1 + 1 + 1
    4
    >>> count_k(4, 4)
    8
    >>> count_k(10, 3)
    274
    >>> count_k(300, 1) # Only one step at a time
    1
    """
```

---

# Thank you!

### Attendance Form -> https://tinyurl.com/adit-disc03

### Anon Feedback -> https://tinyurl.com/adit-anon

### Study Groups -> https://tinyurl.com/adit-study






     