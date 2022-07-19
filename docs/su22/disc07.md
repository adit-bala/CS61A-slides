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

### Trees, Linked Lists

Aditya Balasubramanian
`aditbala [at] berkeley [dot] edu`

---

<!-- 
_class: invert
_footer: 7/18
_backgroundColor: #2222
-->

# Announcements :mega:

- Cats due today
- Ants released tommorow
    - Checkpoint due Friday
- Magic: the Lambda-ing will be released as an extra credit project
    - Smaller project
- HW04, Lab07, due Thursday
- Clobber policy
    - If you do better on final, can clobber midterm
- Midterm Discussion


---

# <!-- fit --> Trees :deciduous_tree::deciduous_tree::deciduous_tree:

---

# `Tree`

* What are they?
    - Data structure for hierarchies of data
* What should we know
    - Recursion!
    - Every subtree is also a `Tree`

---
<!-- 
footer : cred to @Poggenkemper 
_backgroundColor: #2222
 -->


# Tree Terminology
* <span style="color:#e2935b;">Parent Node</span>
    - A node that has branches 
* <span style="color:#279284;">Child Node</span>
    - A node with a parent
    - Can only have one parent
* <span style="color:#233571;">Root</span>
    - The top node in a tree
    - There is only one root for a tree
* <span style="color:#f8d7ca;">Label</span>
    - The value of a node

![bg auto right:45%](https://i.imgur.com/HVIBtFm.jpg)

---
<!-- 
footer : cred to @Poggenkemper 
_backgroundColor: #2222
 -->

# More Tree Terminology
* <span style="color:#1c3678;">Leaf</span>
    - A node with no branches 
* <span style="color:#eb5600;">Branch</span>
    - A subtree of the root
    - All branches are also trees
* <span style="color:#6ba4c8;">Depth</span>
    - How far away a node is from the root
* <span style="color:#1a9988;">Height</span>
    - The depth of the lowest leaf

![bg auto right:45%](https://i.imgur.com/X50smTB.png)

---

<!-- footer: "Slides by Aditya Balasubramanian" -->

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

# Manipulating Trees

## `for b in t.branches`

* What is this?
    - IMPORTANT line for dealing with a `Tree`
* Why use this?
    - Allows us to iterate through branches of a `Tree`
    - Useful for calling recursive functions on all branches of a `Tree`
* Can also be a base case
    - The for loop does not run if there are no branches to iterate over

--- 

# How do I use this? (Recursion for Trees)

1. Base Case
    * Smallest Input
    * Usually a leaf 
2. Recursive Calls
    * Call recursive function on branches
3. Putting it together
    * Use recursive calls to solve problem
    * Can use `max`, `min`, `sum`, `any`, `all` on lists

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

# Thank you!

### Attendance Form -> https://tinyurl.com/adit-disc07

### Anon Feedback -> https://tinyurl.com/adit-anon