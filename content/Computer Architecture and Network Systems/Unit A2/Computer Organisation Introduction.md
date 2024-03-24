
> [!NOTE] Note for the course
> For simplification we will be saying that I/O devices are just data being read from a certain data address

## Programming a circuit
### Hardwired Systems
Hardwire systems are inflexible, they are essentially a "fixed" program for a specific purpose that you cannot reprogram.

These are also called custom chips or ASICs (Application Specific Integrated Circuits)
### General Purpose Systems
On the opposite side the general purpose hardware can do multiple different tasks given control signals.

Instead of having to rewire to create a different program we can simply supply a new set of signals.

Those new control signals are interpreted from instructions written in binary
### The Von Neumann Machine
%%slide 20%%

## Von Neumann Computer
### Fetch Execute Cycle
#### Fetch Cycle
- A register called the Program Counter (PC) holds the address of the next instruction to fetch
- Processor fetches instructions from memory location pointed by PC
- Increment the PC (unless told otherwise)
- Instruction loaded into another register called **Instruction Register** (IR)
- Now we go to the execution
#### Execute Cycle
There are 4 main types of instructions:
- Processor-memory
	- Data transfer between CPU and main memory
- Processor I/O
	- Data transfer between CPU and I/O module
- Data processing
	- Some arithmetic or logical operation on data
- Control
	- Different sequences of operators
	- e.g. jump
*They may be a combination of the above*

## CPU
CPUs require hardware that can perform these actions:
- Fetch Cycles
	- Fetch Instructions
- Execute Cycle
	- Interpret instructions
	- Fetch data
	- Process data
	- Write data
- Instruction Set Architecture (ISA)
	- %%slide 30%%
### N-bit architecture
When we say N-bit (like 64-bit) we mean that the word size for the processor is N-bits.

It usually (but not always) means that the following are also N-bits:
- Instructions
- Internal registers
- Internal interconnect buses
- ALU (performing N-bit operations in a singular cycle)

%%w03_d01_A2_computer_organization-WV.pptx%%
## Stack Machine Vs Register Machine
### Stack Machine
- You can only take from the top %%expand%%
### Register Machine
- You have random access to the memory and can be accessed independently
%%READ FIRST 6 SLIDES OF COMPUTER ORGANIZATION%%



