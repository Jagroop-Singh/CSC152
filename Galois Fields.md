A Field is ...
1. A collection F of objects
2. Two binary operations x and + closed on F.
3. F contains multiplicative identity 1 where (1 x y) = y for all y in F.
4. F contains additive identity 0 where (0 + y) = y for all y in F.
5. For each y in F, there exists a z in F such that (y + z) = 0. (Additive inverse)
6. For each y in F, except 0, there exists a z in F such that (y x z) = 0. (Multiplicative inverse)
7. Associative, commutative, distributive laws work as expected.

Shorthands:
- $a^{-1}$ is a's multiplicative inverse
- a is a's additive inverse
- $a-b$ is short for $a+(-b)$
- $frac{a}{b}$ is short for $a * b^{-1}$
Examples:
- R with standard addition and multiplication form a field.
- Q with standard addition and multiplication form a field.
- Z with standard addition and multiplication DOESN't forma  field. ($a^{-1}$ doesn't exist for most $a$)
- $Z_p$ forms a field with p prime and and addition and multiplication mod p. (p must be prime to make sure every element has a multiplicative inverse.)
Theorem: If a is prime, then there is a field of size $a^n\; for\; each\; n>0$.
- $Z_p$ is not convenient for high-speed processing: mod p is expensive and standard data type don't hold a prime number of values.
- Since 2 is prime there is a field of size $2^n$ for all $n>0$. This is promising because all data types can hold power-of-two different values.
- Galois Fields(Ecariste Galois died age 20 in a duel, 1832)
- The set of all bit sequences of length n forms a field called $GF(2^n)$. We will use $GF(256)$ in this class.
- $GF(256) = {00000000,00000001,00000010,...,11111111}$

Addition:
Interpret the bits as coefficients of a degree 7 polynomial with variable x. 
Add the two polynomials, to keep coefficients 0 or 1, mod each coefficient by 2.
Concat the coefficients of the resulting degree 7 polynomial.
Shortcut: Xor'ing the two bytes produces the same result

Multiplication:
Interpret the bits as coefficients of a degree 7 polynomial with variable x.
Multiply the two polynomials, to keep coefficents 0 or 1, mod each coefficient by 2.
Mod the result by $x^8+x^4+x^3+x+1$
Concat the coefficients of the resulting degree 7 polynomial.
Shortcut: No shortcut. Multiplication is expensive.

Example:
$$
\begin{align*}
00001001 + 10000001\\
x^3+x^0 + x^7 + x^0\\
x^7+x^3+2x^0\\
10001000\\

00001001 * 10000001\\
(x^3+x^0)\;mod\;x^8+x^4+x^3+x+1\\
x^{10}+x^7+x^3+x^0\;mod\;x^8+x^4+x^3+x+1\\
x^7+x^6+x^5+x^2+x^0\\
11100101\\
\end{align*}$$
