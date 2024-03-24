- Operations and their corresponding circuits contain no state
- They correspond to pure functions
- As there is no notion of state, there is no relation to time or sequence
## Overview
AND, OR and NOT (and in some cases, other gates like XOR etc.) can be combined to form complex logic functions. Some functions are very common and used repeatedly in many different designs, including microprocessors. We will discuss these common functions.
## Use Cases
Combinational logic can be used in two different ways:
- For Arithmetic and Logic Operations
	- E.g. Arithmetic and Logic Unit (ALU)
- For control operations
	- E.g. mux, demux, encoder, decoder
## Addition and Subtraction
Addition, subtraction and negation are all done by one circuit: rippleAdd, the "ripple carry adder"
We will proceed in the following stages:
- Adding two bits: halfAdd
	- It can’t deal with addition of two numbers as you can have a carry-in as well
- Adding three bits: fullAdd
	- Once you have an adder that can sum 3 bits, you can combine multiple adders to add numbers of any width
- Adding two integers: rippleAdd
	- Subtracting an integer from another
## Addition
### Half Adder (2 Bits)
To understand how this works we will make a truth table:

| x   | y   | result | c   | s   |
| --- | --- | ------ | --- | --- |
| 0   | 0   | 0      | 0   | 0   |
| 0   | 1   | 1      | 0   | 1   |
| 1   | 0   | 1      | 0   | 1   |
| 1   | 1   | 2      | 1   | 0   |

### Full Adder (3 Bits)
### Binary Word Addition
## Subtraction
### Binary Subtraction
