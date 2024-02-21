https://play.picoctf.org/playlists/13?m=83

- similar to [[vault-door-1]]
```java
public boolean checkPassword(String password) {
	if (password.length() != 32) {
		return false;
	}
	char[] buffer = new char[32];
	int i;
	for (i=0; i<8; i++) {
		buffer[i] = password.charAt(i);
	}
	for (; i<16; i++) {
		buffer[i] = password.charAt(23-i);
	}
	for (; i<32; i+=2) {
		buffer[i] = password.charAt(46-i);
	}
	for (i=31; i>=17; i-=2) {
		buffer[i] = password.charAt(i);
	}
	String s = new String(buffer);
	return s.equals("jU5t_a_sna_3lpm18g947_u_4_m9r54f");
}
```
- lets create a function that reverses this
- create a array with the characters `jU5t_a_sna_3lpm18g947_u_4_m9r54f`
```java
public void printFlag() {
    String s = "jU5t_a_sna_3lpm18g947_u_4_m9r54f";
	char[] buffer = new char[32];
}
```
- going backwards, lets copy the last for loop, but with s instead of password
```java
int i;
for (i=31; i>=17; i-=2) {
	buffer[i] = s.charAt(i);
}
```
- the first 3 for loops continue each other, so we need to find the start of each one, which would be 0, 8, and 16
```java
for (i=16; i<32; i+=2) {
	buffer[i] = s.charAt(46-i);
}
for (i=8; i<16; i++) {
	buffer[i] = s.charAt(23-i);
}
for (i=0; i<8; i++) {
	buffer[i] = s.charAt(i);
}
```
- print flag in the function
```java
System.out.println(new String(buffer));
```
- add our `printFlag();` function to the main
```java
public static void main(String args[]) {
VaultDoor3 vaultDoor = new VaultDoor3();
Scanner scanner = new Scanner(System.in);
System.out.print("Enter vault password: ");
String userInput = scanner.next();
printFlag();
```
- and run and enclose flag in picoCTF{} format