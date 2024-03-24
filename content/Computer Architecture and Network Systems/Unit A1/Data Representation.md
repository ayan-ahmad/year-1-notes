## Overview
Computers must deal with data of different types like: integers, strings, characters, lists, etc.
They are all represented in the computer hardware, which is based on basic electronic components.

To do this we use the voltage through a wire to represent information, computation then requires a manipulation of these voltages.
## Physical Representation
### Analogue
In an analogue input the voltage can take all possible values between a certain range.
This can be extremely fast but it has limited precision, after lots of calculations errors will accumulate to be more inaccurate and it's hard to represent data other than real numbers with this formatting and precision.
### Digital
In a digital input information is expressed using discrete values rather than directly from proportion of voltage. This makes it have good immunity to noise and errors will not accumulate after lots of calculations as a result of such. It can also represent all the data types we use.
#### Binary System
Modern computer use just 2 discrete values of 1 and 0. This is known as binary. It does not matter what voltage you use to represent each discrete value. 5 volts can represent 1 and 0 volts can represent 0. The unit of this is a `bit`.

This allows the circuits to be a lot simpler and reliable only having to represent 2 values. A string of these `bits` can create larger data structures.
#### Physical Quantities
Many physical quantities can represent bits:

| Component | Quantity                 |
| --------- | ------------------------ |
| CPU       | Voltage                  |
| Disk      | Magnetic Field Direction |
| CD        | Surface Pits/Light       |
| Fibre     | Optical Signals          |
| DRAM      | Electrical Charge        |
## Bit
Each signal in a binary system is equal to one bit
## Byte
A byte is a string of 8 bits together
## Nibble
A half of a byte, 4 bits
## Information Capacity of a Bit
The information of $x$ bits is double the amount of $x-1$ bits, this can be represented as $2^x$
## Words
A word is like a byte but it can have any size instead of a set one like 8. 
## Information Capacity of a Word
| Word size (bits) | Numbers of possible values |
| ---------------- | -------------------------- |
| 8                | $2^8 = 256$                |
| 16               | $2^{16} =65536$            |
| 32               | $2^{32}=$                  |
| 64               | Extremely large number     |
## Number Representation
There are several types of numbers and each is represented in a different way.
- Integer
	- Non-negative integers (whole numbers) use binary representation
		- Must be $>=0$
	- Negative integers (whole numbers) use two's compliment
- Real
	- Decimal numbers use floating point
## Decimal and Binary Representation
**
## Binary numbers
Binary representation uses a word of k bits to represent a non-negative number between
**
## Position of Base 10 and Base 2
**
## Sign-Magnitude in Binary
### Why not give a negative symbol
The reason we do not just give a bit for the symbol (+ or -) is because:
- Two different ways to represent 0 (0, -0)
- Different logic for addition and subtracting
## Two's Complement
### What is a compliment
### Calculating Two's Complement
### Range of Numbers
### Information Capacity of Two's Complement
## Binary Arithmetic
## Hexadecimal Notation
### Why?
It's a lot more human readable than binary. Binary is hard to read due to the repetition of numbers but hex shortens it down, makes it more readable and since it's a power of 2 it can have the benefits of binary.
## How
This can represent 4 bits with one letter, here are the values:

| Hex Value | Decimal Value | Binary Value |
| --------- | ------------- | ------------ |
|           |               |              |
## Encoding Non-Numerical Data to Binary
### Colours
Colours are usually represented as "RGB", RGB is a triplet of 3 bytes, encoded in a 32-bit number. Each value is 256 max and it shows the max number.
### Strings
We have standards to ensure uniform representation.
#### ASCII
The most popular and basic 8-bit one is called "ASCII", it contains all English characters and a few punctuation. Each number refers to a different printable or non printable character.
#### Unicode
Unicode is the standard for current text. ASCII is 16-bit with a lot more possible values. ASCII and Unicode values overlap. ASCII has characters in all languages and symbols.
### Images
#### Bitmap
Bit maps are represented by having bits in a 2D Array-esque structure with the bit at each coordinate telling whether or not the location should have an LED turn on or off.
#### Vector