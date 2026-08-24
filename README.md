# 4-bit binary calculator

A 4-bit digital logic circuit designed and simulated in LTspice, followed by physical implementation on a breadboard.

## Overview

This project implements a 4-bit ripple-carry adder using cascaded full-adder stages. The LTspice schematic contains four repeated full-adder structures, with each stage receiving two input bits and a carry input from the previous stage.

The physical prototype was assembled on a breadboard and tested using DIP switches as binary inputs.

## Technical implementation

Each bit stage follows the standard full-adder relationships:

- `Sum = A XOR B XOR Carry_in`
- `Carry_out = (A AND B) OR (Carry_in AND (A XOR B))`

The LTspice schematic contains four stages connected sequentially so that the carry propagates from the least-significant bit to the most-significant bit.

## Inputs and outputs

### Inputs
- `A0–A3`: first 4-bit operand
- `B0–B3`: second 4-bit operand
- `Carry_in`: initial carry input

### Outputs
- `Sum0–Sum3`: four sum bits
- `Carry_out`: final carry

The simulation source uses voltage sources (0 and 1V) for the binary inputs and exposes the sum/carry outputs as labeled nodes.

## Hardware

The prototype was implemented on a breadboard using digital logic ICs and DIP switches for input selection.

The repository includes photographs documenting the prototype at different wiring stages.


## Simulation

Open `simulation/4_bit_binary_calculator.asc` in LTspice.

The original simulation includes a transient analysis directive:

```text
.tran 8m
```

The input sources are configured with binary values in the schematic, allowing individual test cases to be simulated.

## What I learned

- Cascading full-adder stages to construct multi-bit arithmetic logic
- Propagation of carry signals between combinational logic stages
- Translating a simulated digital circuit into a physical breadboard implementation
- Debugging a multi-IC logic circuit through staged testing

## Future improvements

- Add subtraction
- Use Carry Look-ahead adder instead of ripple full adders for quick calculations
- Make a 8-bit version
- Add registers, and memory


