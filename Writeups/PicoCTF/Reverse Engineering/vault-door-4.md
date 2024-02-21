https://play.picoctf.org/playlists/13?m=84
- like [[vault-door-3]]
```java
public boolean checkPassword(String password) {
	byte[] passBytes = password.getBytes();
	byte[] myBytes = {
		106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,
		0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,
		0142, 0131, 0164, 063 , 0163, 0137, 070 , 0146,
		'4' , 'a' , '6' , 'c' , 'b' , 'f' , '3' , 'b' ,
	};
	for(byte b : myBytes) {
		System.out.print((char)b);
	}
	for (int i=0; i<32; i++) {
		if (passBytes[i] != myBytes[i]) {
			return false;
		}
	}
	return true;
}
```
- this one is simple, they have the bytes in the array, so just print out the character that corresponds with the byte
- in the `checkPassword` function, add
```java
for(byte b : myBytes) {
	System.out.print((char)b);
}
```
- run the program and enter a large enough input to pass some checking and ez (wrap in pico thing)