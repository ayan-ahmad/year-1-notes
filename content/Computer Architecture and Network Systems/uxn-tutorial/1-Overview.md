## Uxn
Uxn is an 8-bit stack based virtual computer that has it's own assembly language called Uxntal.
### Memory
The Uxn computer is comprised of four separate spaces:
- a main memory, with 65536 bytes.
- i/o memory, with 256 bytes divided in 16 sections (or devices) of 16 bytes each.
- a working stack, with 256 bytes.
- a return stack, with 256 bytes.
Each byte in the main memory has a 2 byte address whereas i/o memory has an address of 1 byte.

Different areas of the main memory have a different function, we will talk about this in [[2-Locations]].
## Uxntal
### Opcodes
Opcodes are the instructions Uxntal uses to run.

All opcodes have 3 modes:
- Short
- Keep
- Return
#### Short
Seen as `CODE2`.

The short method will take arguments as shorts
#### Keep
Seen as `CODEk.

The keep method will not consume/pop the data that it usually would, i.e. if you add the values you added will stay on the stack
### Return
Seen as `CODEr`.

The return mod generally returns to the "Return Stack" which we will learn in [[4-Stack]]

If the opcode already pushes to the "Return Stack" it will instead push to the working stack
## Terminology
Below is terminology we will be using throughout this tutorial.

| Terms       | Definition                                                                                                                     |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------ |
| Bit         | A bit is a singular 1 or 0 which represents data                                                                               |
| Byte        | A byte is comprised of 8 bits to create larger data<br>*(Most of the functionality will be built off this)*                    |
| Nibble      | A nibble is comprised of 4 bits *(Half a byte)*                                                                                |
| Short       | A short is comprised of 16 bits *(Double a byte)*                                                                              |
| Hexadecimal | Hexadecimal is a representation we use to make binary more readable with a base of 16. Values of `0 -> f` instead of `0 -> 1`. |
| 0x00        | 0x00 or other values represent a hexadecimal value                                                                             |
|             |                                                                                                                                |
