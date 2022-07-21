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

### Scheme

Aditya Balasubramanian
`aditbala [at] berkeley [dot] edu`

---

<!-- 
_class: invert
_footer: 7/18
_backgroundColor: #2222
-->

# Announcements :mega:

- Ants released today
    - Checkpoint due Friday !!!
- Magic: the Lambda-ing has been released
    - OOP based
    - Smaller project (2 points EC)
    - Due 7/28
- HW04, Lab07, due Thursday
- Have Scheme syntax page pulled up whenever coding
- I do read all feedback and your answers to questions!


---

# <!-- fit --> Scheme :detective:

---

# Scheme

* What is Scheme?
    - Another programming language!
    - A dialect of Lisp (**LIS**t **P**rocessor)
* Allows us to bring together all of our previous knowledge
* Recursion based
    - No iterative loops!
    - Only recursion and tree recursion :)

---

# Scheme Primitives

* What is a primitive?
    - Expressions that are simplified or cannot be divided up further
* What are some primitives
    * Numbers -> Floats, Integers
    * Booleans -> Truth-y values, False-y values
* NOTE
    - Everything other than `#f` will evaluate to `True` in Scheme

---

# Scheme Primitives (Example)

<style scoped>
  pre > code {
    font-size: 170%;
  }
</style>

```Scheme
scm> 1
1
scm> 2
2
scm> #t
True
scm> #f
False
```

---

# Defining Variables in Scheme

* How do we define variables in Scheme?
    - Use `define`
* `(define <variable name> <value>)`
    - `(define adit 10)`
    - `adit` -> `10`
    - Evaluates `<value>` and binds the value to `<variable name>` in the current environment.
* ` ' `
    - Accesses the `<variable name>` but not the value
    - Useful for when you don't want to modify the or evaluate the `<variable name>` 

---


# WWSD (Primitives and Defining Variables)

---

# Scheme Call Expressions

* What are Call Expressions?
    - How we invoke functions
* `(<operator> <operand>)`
    - `<operator>` comes first (different than Python)
    (+ 1 2)
* How do we evaluate?
    - Same as Python
    - Evaluate `<operator>`, `<operand>`, and then apply `<operator>` to `<operands>`

---

# WWSD (Call Expressions)

---

# Scheme Special Forms

* What are Special Forms?
    - Look like Call Expressions, but behave slightly differently
* What do they look like?
    - `define`, `if`, `cond`, `and`, `or`, `lambda`, `begin`, `else`

---

# Scheme `if`

* `(if <predicate> <if-true> [if-false])`
    - Evaluate `<predicate>`
    - if `<predicate>` is truth-y
        - evaluate `<if-true>`
    - if `<predicate>` is false-y
        - evaluate `<if-false>`
* `(if (< 4 5) 1 2)`
* `1`

---

# Scheme Booleans

* `and`, `or`, `not`
    - Similar to Python (short-circuits)
* Equivalence
    - `=` -> numbers
    - `eq?` -> check if same object (`is`)
    - `equal?` -> check if contents are the same (`==`)

---

<style scoped>
  pre > code {
    font-size: 170%;
  }
</style>

# Scheme Lambdas

- All functions are Lambdas in Scheme!

```Scheme
scm> (define square (lambda (x) (* x x)))
square
scm> (define (square x) (* x x))          ; Same as above
square
scm> square
(lambda (x) (* x x))
scm> (square 4)
16
```

---
<style scoped>
  pre > code {
    font-size: 180%;
  }
</style>

# Q1: Virahanka-Fibonacci

```python
def virfib(n):
    if n == 0 or n == 1:
        return n
    return virfib(n - 1) + virfib(n - 2)
```

---

<style scoped>
  pre > code {
    font-size: 150%;
  }
</style>

# Scheme Lists

* What are Scheme lists?
    - Linked Lists!!!
* Syntax difference
    - `car <any value>` / `Link.first`
    - `cdr <nil or another Scheme list>` / `Link.rest`

```Scheme
scm> nil
()
scm> (define lst (cons 1 (cons 2 (cons 3 nil))))
lst
scm> lst
(1 2 3)
scm> (car lst)
1
scm> (cdr lst)
(2 3)
```
---

# Worksheet

---

# Thank you!!!

### Attendance Form -> https://tinyurl.com/adit-disc08

### Anon Feedback -> https://tinyurl.com/adit-anon


    