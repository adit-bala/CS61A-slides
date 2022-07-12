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

# <!--fit--> Discussion 06

### Inheritance, Midterm Review

Aditya Balasubramanian
`aditbala [at] berkeley [dot] edu`

---

<!-- 
_class: invert
_footer: 7/12
_backgroundColor: #2222
-->

## Announcements :mega:

- Lab 4 due TODAY (7/12)
- Homework 3 due TOMMOROW (7/13)
- CATS checkpoint due TODAY (7/12)
    - Must add partners on okpy
- Midterm is on THURSDAY 6 - 9 (7/14)
    - Please read the entirety of the [Midterm Logistics Piazza post](https://piazza.com/class/l3b5tbgw9il4kj?cid=339).
    - To request a remote exam, see [this Piazza post](https://piazza.com/class/l3b5tbgw9il4kj?cid=418).
- Mid-Semester Survey at end (15 min at end)

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

# Practice!

---
# Mid-Semester Survey

# [`http://go.cs61a.org/mid-sem-survey`](http://go.cs61a.org/mid-sem-survey)

---

# Thank you



### Attendance Form -> https://tinyurl.com/adit-disc06

### Anon Feedback -> https://tinyurl.com/adit-anon


