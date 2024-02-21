https://play.picoctf.org/playlists/13?m=86
- like [[vault-door-5]]
This vault uses an [[XOR]] encryption scheme.
- to reverse it, we can just XOR the terms we know
- `if (((passBytes[i] ^ 0x55) - myBytes[i]) != 0)` checks if the XOR result is equal to `myBytes[i]` so we can just xor the 0x55 with the myBytes to get the password
```java
public void printFlag() {
	byte[] myBytes = {
		0x3b, 0x65, 0x21, 0xa , 0x38, 0x0 , 0x36, 0x1d,
		0xa , 0x3d, 0x61, 0x27, 0x11, 0x66, 0x27, 0xa ,
		0x21, 0x1d, 0x61, 0x3b, 0xa , 0x2d, 0x65, 0x27,
		0xa , 0x6c, 0x61, 0x6d, 0x37, 0x6d, 0x6d, 0x6d,
	};
	String ans = "";
	for(byte b : myBytes) {
		ans += (char)(b^0x55);
	}
	System.out.println("picoCTF{" + ans + "}");
}
```
- loop through bytes, XOR them and then add them to pwd string
- ez