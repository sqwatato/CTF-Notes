**Common Bitwise Operators:**
- **Bitwise AND (`&`)**: Returns 1 only if both corresponding bits are 1.
    - Example: 5 (101) & 3 (011) = 1 (001)
- **Bitwise OR (`|`)**: Returns 1 if at least one corresponding bit is 1.
    - Example: 5 (101) | 3 (011) = 7 (111)
- **Bitwise XOR (`^`)**: Returns 1 if corresponding bits are different.
    - Example: 5 (101) ^ 3 (011) = 6 (110)
- **Bitwise NOT (`~`)**: Inverts each bit (0 becomes 1, 1 becomes 0).
    - Example: ~5 (101) = 10 (010)
- **Left Shift (`<<`)**: Shifts bits left by specified number, zeros fill in on the right.
    - Example: 5 (101) << 1 = 10 (110)
- **Right Shift (`>>`)**: Shifts bits right by specified number, behavior varies depending on language/signedness.
    - Example: 5 (101) >> 1 = 2 (010) (unsigned), -3 (110) (signed)


- `& 0xFF` ignores all other bits except for the byte at the end, so `101010111111010 & 0xFF = 11111010`