**binwalk** is a tool designed to analyze firmware images and extract embedded files and executable code. This cheatsheet summarizes its key features and usage.

**Basic Usage:**

```
binwalk <image_file>
```

This will analyze the image file and display a report of embedded files and code it identifies.

**Flags:**

- **-e:** Extract identified files.
	- -**Me** to recursively extract
- **-t:** Test extracted files to verify their integrity.
- **-m:** Specify MIME type to filter output.
- **-f:** Specify output format (text, json, csv).
- **--dd:** Deep dump, extract all possible data.
- **-Y, --disasm:** Identify CPU architecture and disassemble code.
- **-V, --verbose:** Increase verbosity of output.
- **-h, --help:** Show help message.

**Advanced Usage:**

- Use regular expressions with `-m` to filter specific file types.
- Combine `-e` and `-t` to extract and verify files automatically.
- Use `-Y` with specific architectures for targeted disassembly.
- Explore custom signature files for specific firmware analysis.

**Examples:**

- Extract all JPEG images from an image file:
    
    ```
    binwalk -e -m 'image/jpeg' image.bin
    ```
    
- Disassemble ARM code sections:
    
    ```
    binwalk -Y arm image.bin
    ```
    
- Extract and verify all possible data:
    
    ```
    binwalk -e -t --dd image.bin
    ```