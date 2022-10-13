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

### Object Oriented Programming, Representation

Aditya Balasubramanian
`aditbala [at] berkeley [dot] edu`

---

<!-- 
_class: invert
_footer: 10/13
_backgroundColor: #2222
-->

## Announcements :mega:

- Homework 5 is due Thursday 10/13
- Ants is due Friday 10/21.
    - Phase 1 checkpoint Friday 10/14.
    - Phase 2 checkpoint Tuesday 10/18.
    - Early submission bonus Thursday 10/20.
- Project parties 5pm-7pm on Wed 10/12, Mon 10/17, & Wed 10/19.

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
# <!-- fit --> Inheritance :family:

---

<!--
_footer: Credit to @Anto and @Poggenkemper
-->

<style scoped>
  pre > code {
    font-size: 140%;
  }
</style>

```python
class Dog():
    def __init__(self, name, owner):
        self.name = name
        self.owner = owner
    def eat(self, thing):
        print(self.name + " ate a " + str(thing) + "!")
    def talk(self):
        print(self.name + " says woof!")

class Cat():
    def __init__(self, name, owner lives=9):
        self.name = name
        self.owner = owner
        self.lives = lives
    def eat(self, thing):
        print(self.name + " ate a " + str(thing) + "!")
    def talk(self):
        print(self.name + " says meow!")
```
---
<!--
_footer: Credit to @Anto
-->
<style scoped>
  pre > code {
    font-size: 140%;
  }
</style>
# What's the problem?

* Too much repeated code
* How to avoid this problem?
* Inheritance!
```python
class Dog(Pet): # Dog inherits the Pet class - as in, all Dogs are Pets
    ...
```
---
<!--
_footer: Credit to @Anto
-->
# Now with Inheritance!
<style scoped>
  pre > code {
    font-size: 140%;
  }
</style>
```python
class Pet():
    def __init__(self, name, owner):
        self.name = name
        self.owner = owner
    def eat(self, thing):
        print(self.name + " ate a " + str(thing) + "!")
    def talk(self):
        print(self.name)

class Dog(Pet): # Inherits all methods/variables from the Pet class
    def talk(self):
        print(self.name + ' says woof!')
```
---
<!--
_footer: Credit to @Anto
-->
<style scoped>
  pre > code {
    font-size: 140%;
  }
</style>
# Inheritance - super()
- `super()` will refer to methods in the parent class
```python
class Cat(Pet): # Inherits all methods/variables from the Pet class
    def __init__(self, name, owner, lives = 9):
        super().__init__(name, owner)
        # same as calling Pet.__init__(self, name, owner) from here
        self.lives = 9
    def talk(self):
        print(self.name + ' says meow!')
```
---
# Worksheet
---
# Representation 
- `__str__`
    - return's a human readable form of object
- `__repr__`
    - return's a human readable form of object

---
# Representation Demo
<style scoped>
  pre > code {
    font-size: 120%;
  }
</style>
```python
class Rational:

    def __init__(self, numerator, denominator):
        self.numerator = numerator
        self.denominator = denominator

    def __str__(self):
        return f'{self.numerator}/{self.denominator}'

    def __repr__(self):
        return f'Rational({self.numerator},{self.denominator})'

>>> a = Rational(1, 2)
>>> str(a)
'1/2'
>>> repr(a)
'Rational(1,2)'
>>> print(a)
1/2
>>> a
Rational(1,2)
```
--- 



# Thank you!

### Anon Feedback -> https://tinyurl.com/adit-anon

