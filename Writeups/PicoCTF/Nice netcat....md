https://play.picoctf.org/practice/challenge/156?page=1

- use [[netcat]] to connect to the server
- it outputs many number which seem to be around the range of 0 to 130
	- hints at ascii
- using python, assuming the numbers are stored in the file `output.txt`
```python
with open('output.txt', 'r') as f:
	data = f.readlines()
ans = ""
for i in data:
	ans += chr(int(i.strip()))
print(ans)
```
