## Labels
To make our code human readable we can use **labels** this provides us human readable names for addresses in memory.

This is like having the following:
```
1 Play games
2 Work out
3 Go shopping
4 Eat breakfast
5 Sleep
```
Instead of having to keep an eye on the number of the instructions and saying "Execute Line 4", we can give these steps labels and say "Execute breakfast".

In Uxn without labels we would have something like this where:
```
|100
( We will learn about JMP/ADD later on this page
  for now all you need to know is JMP goes to the line with that number like the example )
#0200 JMP2
|200
#01 #02 ADD
```
We can implement labels to make the code more readable
```
|100
( We will learn about JMP/ADD later on this page
  for now all you need to know is JMP goes to the line with that number like the example )
;1_plus_2 JMP2 ( We will talk about the ; in the next heading "Addressing" )
|200
@1_plus_2
#01 #02 ADD
```
The addresses for each line will get harder to find as you add more lines in.

Labelling also allows us to create children of a parent label.
- `@` is the parent label
- `&` is the child label
This allows for cleaner code when accessing these labels as child names can be reused as seen below:
```
|100
@something
	&body

@another_thing
	&body
```
## Addressing
When using labels we can't simply just put them in and access the data as shown above. We need pointers to point at these addresses. We will call this addressing the label as we are getting the address for the label.

There are a total of 8 ways to address a label but we will be focusing on 3.
Addressing comes in 2 types:
- Relative
- Absolute

Relative will work +- 1 byte from the current location.
Absolute will take either a byte or a short in an address that points directly where it is.
### Zero Page
To access a label in the zero pages we use  `.label`, this is because zero pages addresses are absolute and stored in only 1 byte which is smaller than the usual short (2 bytes) of regular addresses. This can free up some space doing this.
### General
Generally to access a label in the program we use `;label`, this will point at an absolute address for the provided.
### Child
To access a label of a child whilst in the parent we use `,&label`, the `,` keyword will take a label that's relative and get it's address, we use `&label` to get this relative label.
## Relative Padding
When creating labels we also might want to ensure memory after this point is left untouched. This is done especially with relative padding as shown in the [[3-Storing-Data#Zero Page]].

We do this with the `$num_bytes` keyword. Below shows how the padding saves these locations:
```
|00
0x01   ...       0x17
 |                |
 v                v
@var   $15    @new_var
```
## Accessing
We can store data many ways:
- On the working stack
- On the return stack
- In the zero page
- In memory
### Working Stack
The working stack is as it sounds, it's the stack we use when we want to work on data!

If we want to push data we can simply just place a value

To define a value we typically use `#hex` so if we want to push `50` to the stack we can do: 
```
| 100
#32
```
(`#hex` is actually a short hand for LIT and LIT2 but is a replacement for them as there is no need)

We can also define values in terms of binary by just putting the value like: `00110010`, however this is not used anywhere as it is not readable.

We can put either bytes or shorts on the stack using `#hex`.
### Return Stack
The return stack is used to store addresses which we will need to call back to with the top of the stack typically being the address to return to. If we wish to add any value to the return stack we can use `STH` which takes in `( values )`, this will take the top value on the stack and put it in the return stack.

We will discuss this further in [[4-Stack]] and [[6-Control]].
### Zero Page
The zero page is typically used as a storage for data which we want to store in a global context.
#### Deceleration
If we want to deceleration something in the zero page we can do it like so:
```
|00
@i $1
```
#### Writing
To write to the variable we must use a new Opcode of `STZ`, **S**tore **T**o **Z**ero-page.
This takes in `( value, addr )` and will result in the value in the zero page being changed.

```
|00
@i $1
|100
#05 .i STZ
```
#### Reading
To read to the variable we must use a new Opcode of `LDZ`, **L**oad **D**ata **Z**ero-page.
This takes in `( addr )` and will result in the value being put on the stack.

```
|00
@i $1
|100
#05 .i STZ
.i LDZ
```
### Memory
The memory is typically used as a storage for data which we want to store locally
#### Deceleration
If we want to deceleration something in the memory we can do it like so:
```
|100
@i #01
```
#### Writing
To write to the variable we must use a new Opcode of `STA`, **S**tore **T**o **A**bsolute.
This takes in `( value, addr )` and will result in the value in the absolute address value being changed.

```
|100
#02 ;i STA 
BRK ( We do this as if we don't it will just run the below code and add it to the stack )
@i #01
```
#### Reading
To write to the variable we must use a new Opcode of `LDA`, **L**oad **D**ata **A**bsolute.
This takes in `( addr )` and will result in the value stored at the absolute address being put on the working stack.

```
|100
#02 ;i STA 
;i LDA
BRK ( We do this as if we don't it will just run the below code and add it to the stack )
@i #01
```
