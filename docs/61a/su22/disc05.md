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

# <!--fit--> Discussion 05

### Mutability, Object Oriented Programming

Aditya Balasubramanian
`aditbala [at] berkeley [dot] edu`

---

<!-- 
_class: invert
_footer: 7/7
_backgroundColor: #2222
-->

## Announcements :mega:

- Homework 2 due TODAY (7/7)
- CATS released!!!
    - Can have a partner
    - more time for this project 
- Midterm a week from today
    - all content through today's lecture (inheritance) will be in scope
    - Logistics will come on Piazza
    - Start studying!

---

<!-- 
_backgroundColor: #2222
-->

# <!-- fit --> Mutability :jack_o_lantern:

---

# List Mutation Functions
* append(elem)
    - box `elem` in list and add to end of lst (can lead to nested lists)
* extend(elem)
    - unbox `elem` and add to end (have to use an iterable)
* insert(index, elem)
    - insert `elem` at `index` (don't replace existing elem)
* remove(elem)
    - remove first appearance of `elem` in list (error if not found)
* pop(index)
    - removes and `return` elem at `index` (default arg is end of list)

---

# Mutating Lists

* List Mutation Functions modify **existing** list
* Slicing creates a **new** list
* `a = a + b` creates a **new** list
* `a += b` mutates **existing** list (basically `extend`)
* Indexing into list and changing values modifies **existing** list
    - `a = [1, 2, 3]`
    - `a[0] = 7`

---
<style scoped>
  pre > code {
    font-size: 130%;
  }
</style>

# Indentity vs Equality

* `is`
    - Check if two objects are the same (point to same reference in memory)
* `==`
    - Check to see if content is the same
* Demo
```python
>>> a = [7,6,4]
>>> b = [7,6,4]
>>> a is b
False
>>> a == b
True

```

---

# Shallow Copy and Deep Copy

* Shallow Copy
    - What Python does most of the time
    - Copy top level of list
    - Point to same objects with nested list
* Deep Copy
    - Make completely new copy of list
    - Difficult to do this
* Whenever we copy a sequence, we are using a shallow copy

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
* `self` arguement tells which object to call method on
* Two methods of writing method calls
    - `Class.method(self, args)`
    - `object.method(args)`
        - self is automatically set as object
* [Demo](https://pythontutor.com/composingprograms.html#code=class%20TA%3A%0A%20%20%20%20work_hrs%20%3D%2020%0A%20%20%20%20def%20__init__%28self,%20name,%20grade%29%3A%0A%20%20%20%20%20%20%20%20self.name%20%3D%20name%0A%20%20%20%20%20%20%20%20self.grade%20%3D%20grade%0A%20%20%20%20%20%20%20%20self.overtime%20%3D%200%0A%20%20%20%20def%20work_more%28self,%20hours%29%3A%0A%20%20%20%20%20%20%20%20self.overtime%20%2B%3D%20hours%0A%20%20%20%20%20%20%20%20self.work_hrs%20%2B%3D%20self.overtime%0A%20%20%20%20%20%20%20%20return%20self.overtime%20%2B%20TA.work_hrs%0A%20%20%20%20%0Aadit%20%3D%20TA%28%22adit%22,%202%29%0Ahours_worked%20%3D%20adit.work_more%285%29%0Aprint%28adit.overtime%29%0A&cumulative=true&curInstr=0&mode=display&origin=composingprograms.js&py=3&rawInputLstJSON=%5B%5D)
---

# Thank you!

### Attendance Form -> https://tinyurl.com/adit-disc05

### Anon Feedback -> https://tinyurl.com/adit-anon

