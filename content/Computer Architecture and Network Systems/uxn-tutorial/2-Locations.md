In Uxn we have 2 areas in the main memory:
- The zero page
- The regular page
## Zero Page
The zero page is the first 256 bytes in the program.

In the zero page there are addresses allocated for certain sys calls to the Varvara computer (https://wiki.xxiivv.com/site/varvara.html#system). We will be interfacing these later.

This segment can be accessed using 1 byte as it occupies `00 -> 0f` and is meant for storing data at the runtime of the machine.

To access the Zero Page we must use `|` this gives us padding and puts our code at a certain point in the memory, we will start at `0x00`.
```uxn
| 00
( We are in the zero-page here )
@i $1
```
Do note that we cannot use Opcodes or define values in the zero-page itself.
## Regular Page
The regular page is the rest of the available space. Here we will be writing our code, the program will continue reading instructions and following them until it meets the keyword `BRK`, this keyword stops the execution of the program. We can also change the control of the program as shown in [[6-Control]].

We can access the stack page with a padding any over `0f`. Do note that the padding takes a hexadecimal not binary.
```uxn
| 0100
( We are in the stack-page here )
#00
```