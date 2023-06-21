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

# <!--fit--> Discussion 07

### Single Cycle Datapath


Aditya Balasubramanian
`aditbala [at] berkeley [dot] edu`


---
<!-- 
_footer: ""
-->

## Announcements :mega:


---

## Agenda

- SDS Review
- Single Cycle Datapath

---
<!-- 
_backgroundColor: #3333
-->

# <!-- fit --> SDS Review

---

# Definitions (Pt. 1)

* Clk
    - Central timing unit of the entire SDS; usually only one clock per system
* State element
    - Any clocked element: stores values
    - Only does computation things at the rising edge of the clock
    - E.g. registers
* Logic element
    - Any unclocked elements: does not store value
    - Computes ALL THE TIME!
    - E.g. combinatorial logic elements (AND gates, OR gates, etc.)



---

# Definitions (Pt. 2)

* Flip-flop
    - state element that stores 1 bit's value (0/1)
* Register
    - `n`-bit state element; created with `n` chained FFs
    - `D` = input; `Q` = output
    - Reads value from `D` at clock tick, puts value into `Q`

---

# Definitions (Pt. 3)

* Rising clock edge (RCE)
    - clk goes from 0 => 1; Usually instantaneous
    - Triggers all the state elements dependent directly on the clock
* Falling clock edge
    clk goes from 1 => 0
* Setup time
    - Time BEFORE RCE where input must be stable
* Hold time
    - Time AFTER RCE where input must be stable
* Clock-to-q time (c2q)
    - Time after RCE needed for value in Q to change

---

# Definitions (Pt. 4)

* Combinational logic delay
    - Combinatorial delay between 2 state elements
    - Usually Sum of total delays within the path from the Q of one register to the D of another (or the same) register
* Critical path
    - Total delay between 2 state elements
    - Clk-to-q (reg1) + longest CL + setup time (reg2)
* Maximum clock frequency
    - 1 / minimum clock period

--- 


![bg  width:950](https://i.imgur.com/uE8iKfp.png)

---

# Equations

$\text{max hold time} \leq t_{\text{clock to q}} + \text{shortest CL}$

- Any longer of a hold time means that value has potential to change

$\text{cycle time} \geq t_{\text{clock to q}} + \text{longest CL} + t_{\text{setup}}$

- Cycle time = clock period
- Any shorter cycle time means the values may not finish computing correctly in time

---
<!-- 
_backgroundColor: #3333
-->

# <!-- fit --> Single Cycle Datapath

---

# What Even is a datapath?

- Given a program counter (the address of the instruction we need to execute)
- Update the registers to reflect the given instruction
- Every single update we need to make will be in the RISC-V Reference Card: VERY USEFUL
- Standard datapath accounts for all real RISC-V 32bit instructions
- No pseudoinstructions

---

# Datapath Basics

* Wiring accounts for flow of data
* Control logic block does the hard work of "thinking"
* CL takes data/signal in from datapath ⇒ arrows point towards control logic
    - Instr[31:0]; BrEq; BrLT
* CL feeds signal back to datapath ⇒ arrows point away from control logic
    - Calculates signals to tell datapath what components of datapath to use
    - All other signals in standard datapath

---

# Stages of a Single Cycle Datapath

---

# Instruction Fetch (IF)

1. Update the value in PC
    - (**PCSel** = 0) PC = PC + 4
    - (**PCSel** = 1) PC = ALU output
2. Fetch instruction from IMEM at PC
    - IMEM is “Instruction memory”, generally in the code section!

---




