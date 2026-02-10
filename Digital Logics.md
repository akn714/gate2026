
## Number System
### Arithmetic Overflow and Arithmetic Underflow

- The range of n bit numbers are:
	- if no. is in 1's compliment, then range -> $-\left(2^{n-1}\right) - 1$ to $+\left(2^{n-1}\right) - 1$
	- if no. is in 2's compliment, then range -> $-\left(2^{n-1}\right)$ to $+\left(2^{n-1}\right) - 1$
- *n -> no. of bits*
- If the no. are in this range then it is normal, other wise they are either overflow or underflow
```
NOTE: To avoid overflow, only 1 bit extension is required

Example
a -> n bits
b -> n bits
c = a+b or c = a-b
then, c will not overflow if it has n+1 bits
```

### IEEE 754 floating point representation

## $(-1)^{\text{sign}} \times 1.\text{mantissa} \times 2^{(\text{exponent} - \text{bias})}$

- **Max finite exponent ≠ all 1s (special case)**
- **Max finite exponent = all 1s − 1**
- A number is stored as sign, biased exponent, and mantissa
- **Special cases:**
	- Exponent = all 0s → zero/subnormal;
	- Exponent = all 1s → ∞ (mantissa 0) or NaN (mantissa ≠ 0).
- **32 bits floating point representation**
	- sign - 1 bit
	- exponent - 8 bits
	- mantissa - 23 bits
	- bias - 127
- **64 bits floating point representation**
	- sign - 1 bit
	- exponent - 11 bits
	- mantissa - 52 bits
	- bias - 1023

### Conversion

# $x_{\text{base }y}$ (always y will be greater than x, y>x)

#### Question:
If any no. is multiplies by binary no. then just add 0's at last of binary representation
**Answer:**
<img src="./BIN/Pasted image 20260204025107.png">

---
## Sequential Circuit

---
## Logic Gates

A (xor) B = ( A (xnor) B )'
A' (xor) B = A (xnor) B
A (xor) B' = A (xnor) B
A' (xor) B' = A (xor) B

X (xor) X = 0
X (xor) X' = 1
X (xor) 0 = X
X (xor) 1 = X'

---
# Todos
- SOP, POS
- K-Map