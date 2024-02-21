https://play.picoctf.org/playlists/13?m=87
- like [[vault-door-6]]

This vault uses bit shifts to convert a password string into an array of integers. Hurry, agent, we are running out of time to stop Dr. Evil's nefarious plans!

```java
// Each character can be represented as a byte value using its
// ASCII encoding. Each byte contains 8 bits, and an int contains
// 32 bits, so we can "pack" 4 bytes into a single int. Here's an
// example: if the hex string is "01ab", then those can be
// represented as the bytes {0x30, 0x31, 0x61, 0x62}. When those
// bytes are represented as binary, they are:
//
// 0x30: 00110000
// 0x31: 00110001
// 0x61: 01100001
// 0x62: 01100010
//
// If we put those 4 binary numbers end to end, we end up with 32
// bits that can be interpreted as an int.
//
// 00110000001100010110000101100010 -> 808542562
//
// Since 4 chars can be represented as 1 int, the 32 character password can
// be represented as an array of 8 ints.
//
// - Minion #7816
```

- now we just need to reverse this (sigh)
- first lets write a function to convert a int back into binary with [[Bitwise Operators]]
```java
public byte[] intTobytes(int x) {
	byte[] bytes = new byte[4];
	// shift 24 (3 bytes) so whats left is the first byte
	bytes[0] = (byte)((x >> 24) & 0xFF);
	// shift 16 (2 bytes) so whats left is first 2 bytes, and then take the 2nd byte
	bytes[1] = (byte)((x >> 16) & 0xFF);
	// shift 8 (1 bytes) so whats left is first 3 bytes, and then take the 3rd byte
	bytes[2] = (byte)((x >> 8) & 0xFF);
	// take the last byte
	bytes[3] = (byte)(x & 0xFF);
	return bytes;
}
```
- now we can reverse the steps
```java
public void printFlag() {
	// end array
	int x[] = {1096770097, 1952395366, 1600270708, 1601398833, 1716808014, 1734304867, 942695730, 942748212};
	byte[] bytes = new byte[32];
	// for each num, convert back to byte
	for (int i=0; i<8; i++) {
		int y = x[i];
		byte[] b = intTobytes(y);
		// store byte into bytes array
		bytes[i*4] = b[0];
		bytes[i*4+1] = b[1];
		bytes[i*4+2] = b[2];
		bytes[i*4+3] = b[3];
	}
	// convert bytes array back to string
	String flag = new String(bytes);
	System.out.println("picoCTF{" + flag + "}");
}
```