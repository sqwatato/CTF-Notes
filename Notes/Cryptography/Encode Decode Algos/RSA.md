- [[Asymmetric Encryption Algorithm]]
- Relies on the fact that factorizing a large n is very slow
- RSA public key comes in certificate encoded in [[base64]], and it contains metadata and the key
	- use [[openssl]]  to read certificate
	- `openssl x509 -in n_certificate -text -noout`
##### Steps:
- choose 2 large co-prime numbers $p$ & $q$
- $n = p * q$
- $\phi = (p-1)(q-1)$
- choose an $e$ such that $1 < e < \phi$ and $e$ is coprime of $\phi$
- find $d$ such that $e*d \equiv 1 \mod \phi(n)$
	- use extended euclidean algo to find $d$ with $e$ and $\phi$
- public key: $(e,n)$
- private key: $(d,n)$

##### Cracking:
- if the $n$ small, you can just use a integer factorizer [https://www.alpertron.com.ar/ECM.HTM](https://www.alpertron.com.ar/ECM.HTM) like so to find $p$ and $q$ and calculate the private key

##### Resources 
1. https://www.cs.drexel.edu/~popyack/IntroCS/HW/RSAWorksheet.html
2. https://www.cryptool.org/en/cto/rsa-step-by-step
	1. this one nice
