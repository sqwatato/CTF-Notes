https://play.picoctf.org/practice/challenge/249?page=7

- same as [[PW Crack 4]] but now your pwd u check is the words in dictionary
- to parse `dictionary.txt`
```python
with open('dictionary.txt', 'r') as f:
	pos_pw_list = f.readlines()
```
- then brute force it
```python
for pwd in pos_pw_list:
    pwd = pwd.strip()
    user_pw_hash = hash_pw(pwd)
    
    if( user_pw_hash == correct_pw_hash ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), pwd)
        print(decryption)
    # print("That password is incorrect")
```
- ez