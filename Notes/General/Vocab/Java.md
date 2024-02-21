#### String Format
**Methods:**
- `String.format(String formatString, Object... args)`: Static method on the `String` class. Creates a new formatted string.
- `printf(String formatString, Object... args)`: Static method on the `System` class. Prints the formatted string to the console. Both `format()` and `printf()` use the same format specifiers and arguments.
**Specifying what to format:**
- **`%s`**: Inserts a string.
- **`%c`**: Inserts a single character.
- **`%d`**: Inserts a decimal integer.
- **`%f`**: Inserts a floating-point number.
- **`%o`**: Inserts an octal integer.
- **`%x`**: Inserts a hexadecimal integer (lowercase).
- **`%X`**: Inserts a hexadecimal integer (uppercase).
- **`%%`**: Inserts a literal percent sign (`%`).

**Styling your formatted string:**
- **Flags:**
    
    - `-`: Left-justify
    - `+`: Add sign for positive numbers
    - `0`: Pad with zeros
    - `#`: Add prefix (0 for octal, 0x for hexadecimal)
    - `,`: Group thousands separator
    
- **Width:** Specify minimum field width (e.g., `%10d` for 10-digit integer).
- **Precision:**
    - For integers: minimum number of digits (e.g., `%.2d` for two decimal places).
    - For floats/doubles: maximum number of decimal places (e.g., `%.4f` for four decimal places).