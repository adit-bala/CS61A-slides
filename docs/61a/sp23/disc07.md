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

# <!--fit--> Discussion 07

### Object Oriented Programming

Aditya Balasubramanian
`aditbala [at] berkeley [dot] edu`

---

<!-- 
_class: invert
_footer: 10/13
_backgroundColor: #2222
-->

## Announcements :mega:

- Homework 5 is due Thursday 3/9.
- No live lecture on Wednesday 3/8
    - Watch the 5 lecture videos before attending discussion section.

---

<!-- 
_backgroundColor: #2222
-->

# <!-- fit --> Object Oriented Programming (OOP) :robot:

---
#  Object Oriented Programming (OOP) 
* What is OOP?
    * Use of classes to define our own data types
        - More abstraction
    * Reuse code with inheritance
        - MORE ABSTRACTION
* Those with prior experience in Java are familiar
* You have already used OOP!
    - `list.append`
    - `append` is a method belonging to the `list` class

---

# Some Terminology
* Class
    - Template for creation of object
* Object
    - An instance of a class
* Variables
    * Instance Variables
        - property specific to an object
    * Class Variables
        - property shared between all instances of a class
* Method
    - Function that is bound to a class

---

# Functions vs Methods

* Methods need to take in `self` as an object
* `self` argument tells which object to call method on
* Two methods of writing method calls
    - `Class.method(self, args)`
    - `object.method(args)`
        - self is automatically set as object
* [Demo](https://pythontutor.com/composingprograms.html#code=class%20TA%3A%0A%20%20%20%20work_hrs%20%3D%2020%0A%20%20%20%20def%20__init__%28self,%20name,%20grade%29%3A%0A%20%20%20%20%20%20%20%20self.name%20%3D%20name%0A%20%20%20%20%20%20%20%20self.grade%20%3D%20grade%0A%20%20%20%20%20%20%20%20self.overtime%20%3D%200%0A%20%20%20%20def%20work_more%28self,%20hours%29%3A%0A%20%20%20%20%20%20%20%20self.overtime%20%2B%3D%20hours%0A%20%20%20%20%20%20%20%20self.work_hrs%20%2B%3D%20self.overtime%0A%20%20%20%20%20%20%20%20return%20self.overtime%20%2B%20TA.work_hrs%0A%20%20%20%20%0Aadit%20%3D%20TA%28%22adit%22,%202%29%0Ahours_worked%20%3D%20adit.work_more%285%29%0Aprint%28adit.overtime%29%0A&cumulative=true&curInstr=0&mode=display&origin=composingprograms.js&py=3&rawInputLstJSON=%5B%5D)
---
# Worksheet
--- 



# Thank you!

### Anon Feedback -> https://tinyurl.com/adit-anon

