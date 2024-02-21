https://play.picoctf.org/playlists/13?m=85
In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding!
- see [[vault-door-4]]

```java
public String urlEncode(byte[] input) {
	StringBuffer buf = new StringBuffer();
	for (int i=0; i<input.length; i++) {
		buf.append(String.format("%%%2x", input[i]));
	}
	return buf.toString();
}

public boolean checkPassword(String password) {
	String urlEncoded = urlEncode(password.getBytes());
	String base64Encoded = base64Encode(urlEncoded.getBytes());
	String expected = "JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVm"
					+ "JTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2"
					+ "JTM0JTVmJTY1JTMzJTMxJTM1JTMyJTYyJTY2JTM0";
	return base64Encoded.equals(expected);
}
```
- lets write a function that reverses all this
- firstly, we should write functions to reverse the encoding functions
- for Base64, we can use the decoder instead of the encoder
```java
public String base64Encode(byte[] input) {
	return Base64.getEncoder().encodeToString(input);
}

public String base64Decode(byte[] input) {
	return new String(Base64.getDecoder().decode(input));
}
```
- for the url decoder, we notice the output is going to be like `%63%30%6e%76%33%72%74`, where the numbers are the hexadecimal for the ascii of the character, so we can split the string and add the character of the number
```java
public String urlEncode(byte[] input) {
	StringBuffer buf = new StringBuffer();
	for (int i=0; i<input.length; i++) {
		buf.append(String.format("%%%2x", input[i]));
	}
	return buf.toString();
}

public String urlDecode(byte[] input) {
	StringBuffer buf = new StringBuffer();
	String[] tmp = new String(input).split("%");
	for (String s : tmp) {
		if(s.length() == 2) {
			buf.append((char)Integer.parseInt(s, 16));
		}
	}
	return buf.toString();
}
```
- now we can reverse all the steps!
```java
public void printFlag() {
	String expected = "JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVm"
	+ "JTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2"
	+ "JTM0JTVmJTY1JTMzJTMxJTM1JTMyJTYyJTY2JTM0";
	// reverse base64Encoded
	String base64Decoded = base64Decode(expected.getBytes());
	// reverse url
	String urlDecoded = urlDecode(base64Decoded.getBytes());
	System.out.println(urlDecoded);
}
```
- add the function to the main and run!