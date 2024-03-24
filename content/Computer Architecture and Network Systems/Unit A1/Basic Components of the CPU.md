Modern CPU's are extremely complex however, there are surprisingly only a few basic logic components which are used to construct these CPU's.
## Registers
- Registers are one of the most common building blocks of an integrated circuit.
- CPU registers are **typically**:
	- Parallel in
	- Parallel out
- Other register flavours include:
	- Parallel in -> Serial out
	- Serial in -> Parallel out
	- Serial in -> Serial out

> [!Note]
> Differences in Gated D Latch and D Flip-Flops are negligible for this course

## Control Circuits
A digital circuit such as a CPU is not just doing arithmetic/logical operations on data.

It also needs to conduct control operations
- Choosing between different operations depending on instructions
- Loading data from different locations
- Storing data at different locations
- Etc.

Multiplexers (data selector) %%Finish (Slide 54)%%
### Multiplexer
#### 2 Way
%%Slide 68%%
#### 4 Way

#### Relation of lines and inputs
%%Slide 74%%
### Demultiplexer
This is essentially the reverse of a multiplexer.

This takes in information from one line and distributes to a given number of inputs lines depending on the select input.

This is also called a demux or data distributor
### Bit-Level Vs Word=Level
%%Slide 81%%
## Arithmetic/Logic Unit (ALU)
- Arithmetic
	- Perform operations on numbers for an output (e.g. add, subtract, multiply, divide)
- Logic
	- Performs logics that result in a boolean (e.g. AND, NOT, OR, LT, GT)

The ALU aggregates the functions of all these arithmetic and logical components
## Instructions
### Stacks
#### Stack pointer
##### Circular Stack
#### Reading from a Stack
Multiplexer
#### Writing to a Stack
Demultiplexer