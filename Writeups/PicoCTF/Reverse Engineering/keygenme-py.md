https://play.picoctf.org/practice/challenge/121?page=2

- First locate where the flag will be found
	- In this case the flag needs to be entered by the user correctly
- The flag is verified, so I analyzed the verification to see if I could figure out the flag
- The flag is checked in 2 parts (after length is correct), first:
```python
i = 0
for c in key_part_static1_trial:
	if key[i] != c:
		return False
	i += 1
```
- and second:
```python
if key[i] != hashlib.sha256(username_trial).hexdigest()[4]:
	return False
else:
	i += 1
...
```
- since it compares user entered flag with known values, I changed the code slightly so it would print out the flag
- I deleted all the checking and created a variable, then added the characters that are compared to check if it's right
- In the `check_key` function, I edited the first loop to just loop through the variable and add it to the answer string
```python
...
def check_key(key, username_trial):
    global key_full_template_trial
    # if len(key) != len(key_full_template_trial):
    if False:
        return False
    else:
        ans = ""
        # Check static base key part --v
        i = 0
        for c in key_part_static1_trial:
            # if key[i] != c:
            #     return False
            ans += c
...
```
- Under that, I removed the checking of the hash and rand a quick loop to hash the characters myself and add it to the answer string
```python
	for i in [4,5,3,6,2,7,1,8]:
        ans += hashlib.sha256(username_trial).hexdigest()[i]
```
- `print(ans)` after the loops gave me the correct flag (after adding in the missing `}` )