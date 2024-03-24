There are 3 key ideas to creating a programmable machine:
1. Make it able to perform simple operations (e.g. arithmetic and logic operations in case of a CPU) in a sequence.
2. Allow a way to change the order/sequencing of the program (reprogramming)
3. Make it able to compare two numbers, and then decide what to do next (control the sequence flow)
## Focus of this Unit
%%Slide 9%%
## Machine Language
There are many programming languages. However, each processor architecture has one fixed machine language.
## Machine Vs Assembly
### Machine Language
- The machine executes machine language
	- The program is BINARY words: 0x42c
	- It's possible for a digital circuit/computer to execute
	- No name for instructions or variables, everything is a number
### Assembly Language
- Written by humans for machines
	- The program is human readable text
	- It's easier to read
	- You don't need to remember arbitrary binary operation codes
	- Memory addresses are much easier to handle
## Compiling
Computers cannot directly execute programs in a high-level programming language
- We must translate a program into assembly (and then machine) language
	- This translating from high-level language to assembly language is called compiling
	- This is done by software called a compiler: it reads in a program in e.g. C++ and translates it to assembly language
	- The translation from assembly to machine, a more straightforward process, is done by a software called assembler, which is part of the larger compiler software
		- If you write code directly in assembly (like you will in this course), then you need an assembler rather than a complete compiler.
### Benefits
- A computer can run programs in many languages (using many compilers)
- Compilers can make programming easier: good error messages, etc
- Compilers can optimise the generated code
- Languages can be designed to fit well for different purposes
- For each type of high level language construct, we translate to assembly/machine language following a standard pattern
- Studying these common patterns is the primary learning outcome of this unit

## Instruction Sets
### Elements of an Instruction
- Operation Code (ALWAYS REQUIRED)
	- What to do
- Source Operand Reference
	- To do this
- Result Operand Reference
	- Where to put this
- Next Instruction Reference
	- What to do next
#### Where are the Operands?
Operands can be in one of four areas
- Main Memory
	- Or virtual memory (appear to be in main memory, but may actually be on external storage)
- Processor registers (register machine)
	- If one only (ACCUMULATOR), then implicit reference
	- Otherwise named reference
	- Remember: specialized vs general purpose registers
- On the stack (stack machine)
	- Always implicit reference
- Immediate (e.g. add the number “4” to the contents of the accumulator)
- I/O Device

### Instruction Types
There are 4 types of instructions:
- Data processing
- Data storage
- Data movement (I/O)
- Program flow control
## Instructions
A machine language provides instructions just like a programming language.

Instructions are simple:
- Each instruction typically performs just one operation
- Each instruction had a few operands
### Data Storage (Main Memory) Instructions
- Transfer data between processor and main memory
- Specify
	- Source*
	- Destination
	- Amount of data*
*\* can be implicit*
- May be different instructions for different movements
	- Register -> Regiser or Stack -> Stack
	- Register -> Memory or Stack -> Memory
	- Memory -> Memory
### Data Processing Instructions
#### Arithmetic
- Add, Subtract, Multiply, Divide
- Signed Integer
- Floating Point
- May include:
	- Increment
	- Decrement
	- Negate
#### Logic
- Bitwise operations
- AND, OR, NOT
#### Shift operations
- Shift contents 1 bit left
- Shift contents 1 bit right
- Other versions of shift operators
### Data Movement
%%35%%
### Program Flow and Control Instructions
- Transfer of Control
	- Branch or Jump
	- Skip
	- Subroutine call
- System Control
	- Privileged instructions
	- CPU needs to be in specific state
	- For operating systems use
#### Conditional Vs Unconditional branches
