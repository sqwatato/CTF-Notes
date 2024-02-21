https://play.picoctf.org/practice/challenge/253?page=7

python 
```python
# load message
with open('message.txt', 'r') as f:
    f = f.read()
# remove whitespace on edge and split by space
f = f.strip().split(" ")
# make them all integers
f = map(int, f)
# mod all nums by 37
f = list(map(lambda x: x % 37, f))

ans = ""
for i in f:
    if i <= 25:
        ans += chr(i + ord('A'))
    elif i < 36:
        ans += str(i-26)
    else:
        ans += '_'
print('picoCTF{' + ans + '}')

```