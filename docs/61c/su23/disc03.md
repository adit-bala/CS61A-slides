---
marp: true
theme: default
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

# <!--fit--> Discussion 03

### Floating Point; RISC-V Intro

Aditya Balasubramanian
`aditbala [at] berkeley [dot] edu`


---
<!-- 
_footer: ""
-->

## Announcements :mega:


---

## Agenda

- Floating Point
- RISC-V Intro


---
<!-- 
_backgroundColor: #3333
-->

# <!-- fit --> Floating Point

---

# Floating Point Conversion



![bg right w:650 h:250](https://i.imgur.com/6uGHJll.png)

---

# Decimal -> Floating Point

$$Value = (-1)^{Sign}*2^{Exp + Bias} * 1.mantissa_2$$

10.75

- Convert to Binary w.r.t the floating point
    - `1010.11`
- Shift floating point to match formula format
    - `1.01011 * 2³`
- Read Output
    - `Mantissa =  01100...0`
    - `Exp = 3 - Bias`

---

# Step Size

- Given a certain exponent, step size is the change in decimal value when we add 1 to the mantissa of binary FP
$$2^{exp+bias} * 1.mantissa => 1M...M.MMMM$$
- Step Size is difference between `1MM...M.MMM0` and `1MM...M.MMM1`
- 2¯⁴ in this example

---
<!-- 
_backgroundColor: #3333
-->

# <!-- fit -->RISC-V

---

# Assembly Basics

Assembly is...
- The direct output of compiled code
- Is not the final form of code
- Is still human-readable
- A set of instructions that can be directly understood by the system, after maybe some minor adjustments
- Built up of a single operation at a time
- Even more dumb than regular computer programs
- Read line by line when executed, except when told not to

---

# Storage: Registers

- On-chip memory
- RV32 has 32 of them numbered x0-x31 
- They are all functionally the same but conventionally different
- They're all 32 bits wide
- Anything can be stored in them (no types)
- NOT A VARIABLE

![bg right w:350 h:675](https://i.imgur.com/MlluOlZ.png)

---

# Register Specifics

There are 4 general categories (and some special!):
1. Argument registers: `a0`-`a7`
2. Return value registers: `a0`, `a1`
3. Saved registers: `s0`-`s11`
4. Temporary registers: `t0`-`t6`
Special registers
- Return address: `ra`	NOT RETURN VALUE!!!
Zero: `x0`
Stack pointer: `sp`
Other pointers: `tp`, `gp`

---
<!-- 
_backgroundColor: #3333
-->

# <!-- fit -->RISC-V Greensheet!

---

# Loads


### l<u>x</u> rd imm(rs1)

- Loads `n` bits worth of data from memory address: `rs1 + imm` where `rs1` <u>should</u> already be a valid address.
- `n` will depend on the instruction: `lb` = 8 bits, `lh` = 16 bits, `lw` = 32 bits, `ld` (not used usually) = 64 bits
- If we have too few bits...
    * Sign-extend
- If we have too many bits...
    * Take the 32-most LSB bits!


---


# Stores


### s<u>x</u> rd imm(rs1)

- Saves `n` bits worth of data to the memory address: `rs2 + imm`
- Truncates to `n` LSB bits to be stored

---

# Jump Instructions, `jal`, `jalr`, `j`, `jr`


|  | Saves return address  | Jump and no return |
|:-----------  | :----------- | :----------- |
| **PC-relative address** | `jal ra, label`  | 	`j label`   |
| **Address in a register** |   `jalr ra, rs1, imm`  | 	 `jr rs1`   |

`j` and `jr` are shorthand for common combinations of certain instructions and register usages.
```Assembly
j label # jal x0, label
jr rs1 # jalr x0, 0(rs1)
```

---

# Thank you


