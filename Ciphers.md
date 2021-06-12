## Block Cipher
Most famous Block Cipher right now is #AES
assembly languages implement and support block ciphers so that you can exexute block
ciphers in 10 cpu cycles
Block ciphers takes an input that's a key, and when you give it a key, it gives you back a permutation, conceptually the bock cipher takes a key and returns a permtuation
The property it has, is that a block cipher with a random key is indestinguishable from a random permutation
# Block Cipher Modes of Operation
## ECB (Electronic Codebook)
![[Pasted image 20210610141644.png]]
AES: b = 128
b = 128 : Block Size
$$let\; p:\{0,1\}^b \rightarrow\{0,1\}^b$$
![[Pasted image 20210610145547.png]]
## CBC (Cipher Block Chaining)

![[Pasted image 20210610134642.png]]
IV : Initialization Vector
We take the initialization vecotor, and we xor it with the first block before it gets to the plain text.
IV is random b bits, per encryption.
If cipher text for plain text was the same, then you would have a leak, so we want to randomize the cipher text, so that the same plain text encrypted twice would have different cipher texts as long as the IV bits are random.

## CTR (Counter)
![[Pasted image 20210610135646.png]]
![[Pasted image 20210610135947.png]]
![[Pasted image 20210610141316.png]]

## OFB (Output Feedback)
![[Pasted image 20210610141532.png]]

# Security Model for Encryption
Real encryption should be indistinguishable from random.
This is quantified by a distinguishing game
![[Pasted image 20210610144435.png]]