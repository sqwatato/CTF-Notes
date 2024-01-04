- Ton of encrypt and decryption algos

##### Usage
- Encode
	- `openssl aes256 -in <encrypted_file> -out <decrypted_file> -k <password>`
- Decode
	- `openssl <algo> -d -in <encrypted_file> -out <decrypted_file> -k <password>`
- Flags
	- `-salt` ngl idk but apprently adds some rando things to make it more secure?
##### Algos
- [[AES]] - (128, 192, 256)