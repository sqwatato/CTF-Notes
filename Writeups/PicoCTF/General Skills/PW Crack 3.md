https://play.picoctf.org/practice/challenge/247?page=6
- Similar to [[PW Crack 2]]
- notice
- `pos_pw_list = ["f09e", "4dcf", "87ab", "dba8", "752e", "3961", "f159"] `
- write a python loop to test every password and add it to the code
```python
pos_pw_list = ["f09e", "4dcf", "87ab", "dba8", "752e", "3961", "f159"]

for pwd in pos_pw_list:
    user_pw_hash = hash_pw(pwd)
    
    if( user_pw_hash == correct_pw_hash ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), pwd)
        print(decryption)
    print("That password is incorrect")

```
- there's ur flag
