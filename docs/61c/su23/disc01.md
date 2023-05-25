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
footer: "Credits to Rosalie Fang"
---

<!-- 
_paginate: false
_footer: Slides available at [`teaching.aditbala.com`](https://teaching.aditbala.com)
_class: invert
-->

# <!--fit--> Discussion 01

### Number Representation

Aditya Balasubramanian
`aditbala [at] berkeley [dot] edu`

---

## About Me

- Grade: Junior
- \# Teaching Sem: `4`
    - 61a: `3`
    - 61c: `1`
- Major: Computer Science
- Origin: <!-- 
_class: invert
_footer: __/__
_backgroundColor: #2222
-->Maryland
- Hobbies:
  * Reading, Gymming, Bouldering (?)

![bg right](https://i.imgur.com/WNUiTk7.jpg)

---


## Announcements :mega:


---

## Agenda

- Intro
- Unsigned
- Sign-Magnitude
- 2's Complement
- Q & A

---

## Number Representation

* Everything is bits!
* Numbers
    - 19 -> `0b00001011`
* ASCII Characters
    - Even letters and punctuation can be represented with bits
    - `a` -> `0b1100001`
* Computer Instructions
    - `3 + 0` -> `0b00000000001100000000000010010011`

---

# Conversions between Representations

- Base *a* to decimal
    - \__ __ __ __ __ __ __ __
       a⁷ a⁶ a⁵ a⁴ a³ a² a¹ a⁰ 
    - Example: 61
    - Binary: `0b0111101`
    - Octal (Base 8): `75`
    - Hex (Base 16): `3D`
- Binary to Hex
    - Convert groups of 4 bits at a time
    - Example: `0b00111100`
    - What if length is not multiple of `4`?

--- 

# Speedy Conversions

- `2ⁿ` -> `n+1` bit is `1`, rest are `0`
    * `64 = 2⁶ = 0b01000000`
- `2ⁿ - 1` -> `n-1` bits that are all 1
    * `63 = 2⁶ - 1 = 0b00111111`

---

# Unsigned

- Range: [`0`, `2ⁿ¯¹ - 1`]
- \__ __ __ __ __ __ __ __
   2⁷ 2⁶ 2⁵ 2⁴ 2³ 2² 2¹ 2⁰

---
<!-- 
_class: invert
_footer: __/__
_backgroundColor: #8888
-->

# What about negative numbers?

#### Q: How to identify if a number is representable or not in a certain binary notation?

#### A:


- Check if the number is in the range of the representable numbers
- As a clarifying check, try to convert it to binary, then look at the binary and convert it back - is it the same number?

---

# Sign-Magnitude Notation

- Range: `[-(2ⁿ¯¹ - 1), 2ⁿ¯¹-1]`
- \____ __ __ __ __ __ __ __
   sign 2⁶ 2⁵ 2⁴ 2³ 2² 2¹ 2⁰
- `-1^sign * magnitude` (convert normally)
- Pros
- Cons
    - `+0` and `-0`
    - addition?

---

# Two's Complement

- Range: `[-2ⁿ¯¹, 2ⁿ¯¹-1]`
- \____ __ __ __ __ __ __ __
   -2⁷ 2⁶ 2⁵ 2⁴ 2³ 2² 2¹ 2⁰
- `-1^sign * magnitude` (convert normally)
- Positive: same as unsigned
- Negative: `~(positive) + 1`

---

# Bias Notation

- Range: `[bias, 255 + bias]`
- Applying a shift to the unsigned interpretation of number
- Bias is typically negative
    - Standard bias: `-(2ⁿ¯¹-1)`
- Converting to bias notation
    - `x + b = n`
    - `x` = binary in bias notation
    - `b` = chosen bias
    - `n` = number want to represent
- When is bias notation useful?

---

# Thank you!

### Feedback 