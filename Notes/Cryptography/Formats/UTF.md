- Unicode Transformation Format
- UTF-8 and UTF-16 and stuff
```python
string = "Hello, world!"
encoded_string = string.encode("utf-16")
print(encoded_string)  
# Output: b'\xff\xfeH\x00e\x00l\x00l\x00o\x00,\x00 \x00w\x00o\x00r\x00l\x00d\x00!\x00'
decoded_string = encoded_string.decode("utf-16") print(decoded_string) # Output: Hello, world!
```
