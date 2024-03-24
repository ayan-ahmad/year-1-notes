## Register Files
### During Clock Tick
Each clock tick we evaluate if the load data line (ld) is high, if it is we set the registers value to the value in the data line (d)
### During Clock Cycle
%%slide 8%% 
## Top Down
%%Slide 9%%
## User Visible Registers
These are accessible VIA machine/assembly code
### General Purpose

### Specialized
- Data (e.g. Accumulator)
- Address
- Segment pointer
- Index register
- Stack pointer
- Condition Codes (Flags)
	- User-visible, but not writeable

The trade-off between general purpose and specialized is flexibility vs efficiency.
## How Wide
%%Slide 12%%
## Control & Status Registers
These are used to control the operation of a processor. They are generally not user visible.

Some typical registers are:
- Program Counter: Address of next instruction to be executed
- Instruction Register: The instruction being currently executed
- Memory Address Register:  The address to be read from memory
- Memory Buffer Registers: The data read from, or being written to memory
- Program Status Word (PSW)
Different processors may have different names for them.
### Program Status Word
%%Slide 14%%
## Register Organization Example
%%Slide 15%%

%%Ignore 17-20%%