# Bitwise Operations
A value can be thought of as a sequence of bits
Bitwise logical operations treat each bit as true(1) or false(0), and compute all in parallel.
```
~x		=	Logical NOT	\\ Reverse every bit
x | y	=	Logical OR	\\ Output is true if any input is true
x & y	=	Logical AND	\\ Output is true if both inputs are true
x ^ y	=	Logical XOR \\ Output is true only if both inputs are different
x >> n	=	Bitwise Right Shift \\ Shift bits in x n positions to the right
x << n	= 	Bitwise Left Shift \\ Shift bits in x n positions to the left
 
Set a particular bit to 1
x = x | (1 << i); // Bit indices traditrionally start on the right
Moves 1 to its proper bit position, the or forces ith position to be 1

Clear a particular bit to 0
x = x & ~(1 << i);
Moves 1 to its proper bit position, flip every bit, and forces ith position to be 0

Get a particular bit
x = 1 & (x >> i);
moves bit to far right position, and operation outputs 1 if bit is 1 otherwise 0

Rotate the bits of x left i positions
hi 	= x << i;		// copy x shifted left i positions
lo 	= x >> (32-i);	// copy x bits that disapppeared to low i positions
x 	= hi | lo;		// reassemble

To reverse the order of the bytes in uint32_t x
a = (x & 0x000000FF) << 24;		// copy byte 0 and shift left 24 bits
b = (x & 0x0000FF00) << 8;		// copy byte 1 and shift left 8 bits
c = (x & 0x00FF0000) >> 8;		// copy byte 2 and shift right 8 bits
d = (x & 0xFF000000) >> 24;		// copy byte 3 and shift right 24 bits
x = a | b | c | d;				//reassemble