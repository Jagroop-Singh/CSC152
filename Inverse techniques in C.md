## AXR
AXR - Addition, XOR, Rotate
If these three operations are applied, their result is invertable
$$
\begin{align*}
x = x + y;\\
x = x - y;\\\\

x = x ^ y;\\
x = x ^ y;\\

x = x >> y;\\
x = x << y;\\
\end{align*}
$$
``` 
uint32_t scramble(uint32_t x) {
	x = x ^ 0x1AFE9B3A
	x = x <<< 12;
	x = x + 0x2783AFBC;
	return x;
}
```
``` 
uint32_t unscramble(uint32_t x) {
	x = x - 0x2783AFBC;
	x = x >>> 12;
	x = x ^ 0x1AFE9B3A
	return x;
}
```
Because the scramble used invertible opertaions, we can decrypt it by doing the inverse operations in the opposite order.

## Feistel Network or Construction 
The construction itself is invertible and not the components
### Feistel
This is an example of a Feistel Structure
```
void fscramble(uint32_t *x){	//x points to array of two uint32_t
	x[0] = x[0] ^ f(x[1]);		// f returns random looking uint32_t
	x[1] = x[1] ^ g(x[0]);		// g returns random looking uint32_t
}
```
```
void funscramble(uint32_t *x){	//x points to array of two uint32_t
	x[1] = x[1] ^ g(x[0]);		// g returns random looking uint32_t
	x[0] = x[0] ^ f(x[1]);		// f returns random looking uint32_t
}
```
g is usually the same as f to keep the code small
The components({f,g}) of a Feistel structure do not need to be invertible
### Feistel Encoding
#Feistel
Four Steps

