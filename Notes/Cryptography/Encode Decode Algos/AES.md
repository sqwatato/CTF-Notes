- [[Symmetrical Encryption Algorithm]]
- [[Block Cipher]]

- welp idk how it works (yet) but
- `openssl aes-256`

##### 2 modes
- ECB
	- based on key length, break plaintext into chunks, so [128]-[128]...
	- same message will give same result, insecure
	- does not encrypt message well, some data still visible
	- attacker could swap portions that are known to be like date sent and screw up data
- CBC
- ![[Screenshot 2024-01-03 at 10.38.54 PM.png]]
	