https://play.picoctf.org/playlists/13?m=82

This vault uses some complicated arrays! I hope you can make sense of it, special agent.
- similar to [[vault-door-training]]
- initially we see the check password function which exposes the password in a annoying way
```java
public boolean checkPassword(String password) {
        return password.length() == 32 &&
               password.charAt(0)  == 'd' &&
               password.charAt(29) == '9' &&
[...]
```
- we could manually construct the flag, or we can try to do some nice copy pasting to print the flag
- I edited the `checkPassword` function so it will store the supposed character at the charAt spot in a array, so we can print the flag
- so create the array, and use cmd f to changed the copied code
```java
char[] buffer = new char[32];
buffer.charAt(0)  == 'd' &&
buffer.charAt(29) == '9' &&
[...]
```
- more cmd f to remove the charAt and replace with indexing \[\] 
```java
char[] buffer = new char[32];
buffer[0)  == 'd' &&
buffer[29) == '9' &&
```
- and replace the parenthesis with a bracket and make double == a single one
- for cmd f purposes, i used `\)\s*==` regex to match the equals and ), since the spaces were not always right
- now replace all the `&&` with a `;`
```java
char[] buffer = new char[32];
buffer[0] =  'd' ;
buffer[29] =  '9' ;
```
- now add the print statement!
```java
[...]
buffer[31] =  'e';
System.out.print("picoCTF{");
for(char c : buffer) {
	System.out.print(c);
}
System.out.println("}");
```
- run program
- yaya