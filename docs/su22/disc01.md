---
marp: true
theme: gaia
class: invert
style: |
    section {
        font-size: 160%;
    }
paginate: true
footer: "Slides by Aditya Balasubramanian"
---

<!-- 
_paginate: false
_footer: date
_class: lead invert
-->

# <!--fit--> Discussion 01

### Control, Environment Diagrams

Aditya Balasubramanian
`aditbala [at] berkeley [dot] edu`

---

# Announcements

---

<!-- 
_class: lead invert
-->

# <!-- fit --> Control :robot:

---

<!-- 
_class: lead invert
-->

# Booleans


Falsey|Truthy
:--|:--
`False`|`True`
`None`|Everything else
`0`||
`[]`, `""`, `()`, `{}`||

Some `<conditional expressions>`  that will evaluate to either False/True most of the time, with a few exceptions later into the semester.

---

<!-- 
_class: lead invert
-->

# Boolean Operators

* `not <conditional expression>`
    * returns opposite of `<conditional expression>`
    * `not (1 == 2)` -> `True`
* `<conditional expression> or <conditional expression> `
    * returns the first **Truthy** value it finds, `False` if none
    * `0 or None or 1` -> `1`
* `<conditional expression> and <conditional expression> `
    * return first **Falsey** value, or last value if everything is true
    * `40 and 0 and True` -> False
    * `40 and 1 and True` -> True

---

<!-- 
_class: lead invert
-->

## Short Circuiting

* Sort of like making an assumption
    * if I'm broke, then I don't need to check the price of boba since I'll never be able to buy it

* `and` will stop at the first **Falsey** value and return it

* `or` will stop at the first **Truthy** value and return it
* Why is this important?
    * May not need to evaluvate all expressions. Even if there is an expression that errors, e.g. `1/0`, and/or expression might short circuit before it reaches error

---

<!-- 
_class: lead invert
-->

## Boolean Examples

* `0 or 435 or False`
    * returns `435`
* `True and "Hello" and 0`
    * returns `0`
* Short Circuiting
* `3 and 1/0 and False`
    * returns `Error`
* `3 and False and 1/0`
    * returns `False`

---

<!-- 
_class: lead invert
-->

## If Statements

```python 
if <conditional expression>:
    <suite of statements>
elif <conditional expression>:
    <suite of statements>
else:
    <suite of statements>
```

- Colons after `if`, `elif`, `else` statements
- `else` doesn't need `<conditional expression>`

---

<!-- 
_class: lead invert
-->

## If Statements Example

```python 
wallet = 0

if wallet > 0:
    print('you are not broke')
else:
    print('you are broke')
if wallet == 0:
    print(0)
```

* Output ->
    * you are broke
      0

---






