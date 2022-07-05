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

# <!--fit--> Discussion 04

### Sequences

Aditya Balasubramanian
`aditbala [at] berkeley [dot] edu`

---

<!-- 
_class: invert
_footer: 7/5
_backgroundColor: #2222
-->

## Announcements :mega:

- Hog due TODAY for EXTRA CREDIT (7/5)
- No extensions for EC unless you have specific accomodations
- HW2 due Thursday (July 7th)
- Cats (Project 2!) begins Thursday
  - Checkpoint next Tuesday (July 12th)
  - Due following Tuesday (July 19th)
- Instructor OH - conceptual help; super useful!



---

# Questions from last discussion

- What is in-scope for the exam
  - All lecture prior to the week of the exam
  - Practice exams until Summer 2019
  - Would personally reccomend doing more if you feel shaky (start soon)

---

<!-- 
_backgroundColor: #2222
-->

# <!-- fit --> Lists :clipboard:

---

## Lists

- An indexed collection of any data type
- Examples of valid lists:
    - `[1, 2, 3]`
    - `[True, False, 'boo']`
    - `[[4], [3, 6, 7], [8]]`

--- 

## Creation and Usage
<style scoped>
  pre > code {
    font-size: 140%;
  }
</style>
<!-- 
style: |
    section {
        font-size: 160%;
    }
-->

* In order to access the values in our list, we have to use the index
* Python lists are zero indexed, so the first element is at index 0
* `n` element is at `n-1` index
* Can also access elements in reverse order through negative index
    - Last element is accessed through index `-1` or `len(list) - 1`
```python
>>> a = [1, 2, [3, 4]]
>>> a[0]
1

>>> a[2]
[3, 4]

>>> a[2][0]
3
```

---

# Q3: WWPD (Lists)

---

## List Slicing

* How do you access a subset of the list?
* List slicing: creating a copy of part of the list
    * Syntax: `list[<start index>: <non inclusive end index>: <step size>]`
    * step size by default is 1
    * negative step size means list is reversed


--- 

## List Slicing Examples
<style scoped>
  pre > code {
    font-size: 175%;
  }
</style>

```python
>>> a = [7, 89, True, ['cat']]

>>> a[1:3]
[89, True]

>>> a[:3:2]
[7, True]

>>> a[::-1]
[['cat'], True, 89, 7]

>>> a[:3:-1]
[]
```

---

## List Comprehension

* How do you create a list that fits some criteria?
e.g. How would you create a list with numbers 1 - 4, but squared
`[1, 4, 9, 16]`
* List Comprehension: creating a list based on expressions filtering other lists
* Syntax: `[<expression> for <value> in <sequence> if <fitler>]`
* `if` condition is optional

---

## List Comprehension Examples
<style scoped>
  pre > code {
    font-size: 175%;
  }
</style>

```python
>>> a = [x**2 for x in range(1, 5)]

>>> a
[1, 2, 9, 16]

>>> [x/2 for x in [x for x in a if x % 2 == 0]]
[1, 8]

```
---

# Q4: Even weighted

---

# Q5: Max Product

---

# Sequences :one: :two: :three:

---

# Sequences

* Many languages provide `map`, `filter`, `reduce` functions for sequences (lists in Python) 
* Help manipulate lists with built-in functions

---

# Q1: Map, Filter, Reduce

---

# Q2: Count Palindromes

---

<style scoped>
  pre > code {
    font-size: 145%;
  }
</style>

# Dictionaries :book:

* Maps `keys` to `values`
* Doesn't really have an order
* Access elements using `keys` rather than indices

---

# Dictionaries :book:

- Maps `keys` to `values`
- Doesn't really have an order
- Access elements using `keys` rather than indices
- Defined with curly braces (`{}`)
  - `{key: value}`

Demo:

```python
pokemon = {'pikachu': 25, 'dragonair': 148, 25: 'hello'}
pokemon['pikachu'] # 25
pokemon['hello'] = 'hi'
pokemon # {'pikachu': 25, 'dragonair': 148, 25: 'hello', 'hello': 'hi'}
```

---

# Q6: WWPD (Dictionaries)

---

# Thank you

### Attendance Form -> https://tinyurl.com/adit-disc04

### Anon Feedback -> https://tinyurl.com/adit-anon