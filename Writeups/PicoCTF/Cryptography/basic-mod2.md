https://play.picoctf.org/practice/challenge/254?page=7

- similar to [[basic-mod1]] but with a lil twist?
- i copied geeksforgeeks mod inverse code and tweak numbers from last time

```python
# load message
with open('message.txt', 'r') as f:
    f = f.read()
# remove whitespace on edge and split by space
f = f.strip().split(" ")
# make them all integers
f = map(int, f)

def modInverse(A, M):
 
    g = gcd(A, M)
 
    if (g != 1):
        print("Inverse doesn't exist")
 
    else:
 
        # If A and M are relatively prime,
        # then modulo inverse is A^(M-2) mod M
        # print("Modular multiplicative inverse is ",
        #       power(A, M - 2, M))
        return power(A, M - 2, M)
 
# To compute x^y under modulo M
 
 
def power(x, y, M):
 
    if (y == 0):
        return 1
 
    p = power(x, y // 2, M) % M
    p = (p * p) % M
 
    if(y % 2 == 0):
        return p
    else:
        return ((x * p) % M)
 
# Function to return gcd of a and b
 
 
def gcd(a, b):
    if (a == 0):
        return b
 
    return gcd(b % a, a)

# mod 41 and find the modular inverse
f = [modInverse(i%41, 41) for i in f]

ans = ""
for i in f:
    if i <= 26:
        ans += chr(i + ord('A')-1)
    elif i < 37:
        ans += str(i-27)
    else:
        ans += '_'
print('picoCTF{' + ans + '}')

```