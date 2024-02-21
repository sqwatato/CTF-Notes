The **Least Significant Bit (LSB)** refers to the **rightmost bit** in a binary representation of a number. It has the **smallest weight** and contributes the **least amount** to the overall value compared to other bits.

### Calculating the LSB:

There are two ways to approach calculating the LSB, depending on the context:

**1. For a specific binary number:**

- The easiest way is to simply **look at the rightmost bit**. If it's 1, the LSB is 1; if it's 0, the LSB is 0.
- You can also use **bitwise AND operation** with 1. In most programming languages, this is denoted by `& 1`. This operation sets all bits except the LSB to 0, effectively isolating it.

**2. For the resolution of a system (e.g., analog-to-digital converter):**

- You need to know the **system's resolution** (number of bits used) and its **full-scale range** (the range of values it can represent).
- The common formula is **LSB = Full-Scale Range / 2^(Resolution - 1)**. This accounts for the contribution of all bits except the LSB.

**Example:**

- Consider a 10-bit system with a full-scale range of 1024 units.
- Using the formula, LSB = 1024 / 2^(10 - 1) = 2.

This means that in this system, changing the LSB represents a difference of 2 units.

### Key Points:

- The LSB is the most sensitive bit in terms of changes. Flipping it has the smallest impact on the overall value.
- Understanding the LSB is crucial in various fields like digital signal processing, image compression, and cryptography.