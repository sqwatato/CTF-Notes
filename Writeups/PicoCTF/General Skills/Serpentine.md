https://play.picoctf.org/practice/challenge/251?page=7

looking at the code, we see the `print_flag()` function, so we want to try to call it
```python
def print_flag():
  flag = str_xor(flag_enc, 'enkidu')
  print(flag)
```
right before the main function is called, try to call the print_flag function
```python
if __name__ == "__main__":
  # start of inserted code
  print_flag()
  # end of inserted code
  main()
```
- scroll to the start of the terminal and there it is