https://play.picoctf.org/practice/challenge/261?page=7

- it is a [[tar]] file, so `tar -xvf leak.tar` will unzip it and create a folder with usernames and passwords .txt
- since the line number the username is on corresponds with the password line number, we just need to find cultiris line number
```python
with open('leak/usernames.txt', 'r') as f:
    user = f.readlines()
with open('leak/passwords.txt', 'r') as f:
    pwd = f.readlines()

for i in range(len(user)):
    if user[i].strip() == 'cultiris':
        print(pwd[i].strip())
```
- we get the flag `cvpbPGS{P7e1S_54I35_71Z3}`
- since the brackets remain the same, it looks like a [[ROT13]], so going into [[CyberChef]] we get the flag
