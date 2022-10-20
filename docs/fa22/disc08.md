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

# <!--fit--> Discussion 08

### Linked Lists, Mutable Trees, Efficiency

Aditya Balasubramanian
`aditbala [at] berkeley [dot] edu`

---

<!-- 
_class: invert
_footer: 10/13
_backgroundColor: #2222
-->

## Announcements :mega:

- Homework 6 is due Thursday 10/20.
- Ants is due Friday 10/21.
    - Early submission bonus Thursday 10/20.
- Project party 5pm-7:30pm Wed 10/19.
- Midterm 2 is 8pm-10pm Thursday 10/27.
- Read Midterm 2 logistics [post](https://edstem.org/us/courses/25379/discussion/1983557)
- Guest lecture on Web Apps by Pamela Fox on Monday 10/24.

---
# Clarifications

- **Mutating** vs **Returning New**

---


# <!-- fit --> Linked List :flushed: :fast_forward: :flushed: :fast_forward: :flushed:

---

# Linked Lists

- Can be thought of as a queue waiting to enter a place (starting from the end of the line)
- Each person only knows themself and who is in front of them (rest of the line)

---

# Linked Lists (In More Formal Terms)

* An object that either has a `first` and `rest` attribute or is empty
* `rest`
    - Must be `Link.empty` or another Linked List
    - Recursive data type!
* `first`
    - Any data type

![auto vertical:50%](https://i.imgur.com/c0tLN7C.png)
   
---

<style scoped>
  pre > code {
    font-size: 145%;
  }
</style>

# Linked List Example

```python
one = Link(1, Link(2, Link(3)))
>>> one.first
1
>>> one.rest
Link(2, Link(3))
>>> one.rest.rest
Link(3)
>>> one.rest.rest.first
3
>>> Link(Link(1), Link(2, Link(3)))
>>> Link(1, 2)

```

---
# Worksheet :smiley:

---

# <!-- fit --> Mutable Trees :deciduous_tree::deciduous_tree::deciduous_tree:

---

# `Tree`

* Initializing a `Tree`
    -  `Tree(label, branches=[])`
    - `t = Tree(1, [Tree(2), Tree(3)])`
* Accessing branches of a `Tree`
    - `t.branches` -> `[Tree(2), Tree(3)]`
* Checking if a `Tree` is a leaf
    - `t.is_leaf()` -> `False`
    - `t.branches[0].is_leaf()` -> `True`
* Getting label of a `Tree`
    - `t.label` -> `1`

---

<style scoped>
  pre > code {
    font-size: 160%;
  }
</style>

# `Tree` Implementation

```python
class Tree:
    def __init__(self, label, branches=[]):
        for b in branches:
            assert isinstance(b, Tree)
        self.label = label
        self.branches = branches

    def is_leaf(self):
        return not self.branches
```

---

# Worksheet

------ 

# Thank you!

### Anon Feedback -> https://tinyurl.com/adit-anon

