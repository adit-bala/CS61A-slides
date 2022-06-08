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

### Recursion

Aditya Balasubramanian
`aditbala [at] berkeley [dot] edu`

---

<!-- 
_class: invert
_footer: date
_backgroundColor: #2222
-->

# <!-- fit --> Announcements :mega:

---

<!-- 
_backgroundColor: #2222
-->

# <!-- fit --> Recursion :dolls:

---

## Recursion

* What is a recurisve function?
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
    * How can I use solution for smaller problems to solve original problem
    * **Add each layer until you get to the smallest doll**

---

[ADD PROBLEMS]
     