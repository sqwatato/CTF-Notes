
- testing out the program, and viewing code, we need 100000 bucks to get the flag
```c
if(account_balance > 100000){
	FILE *f = fopen("flag.txt", "r");
```
- the only time our money changes is in this transaction
```c
scanf("%d", &number_flags);
if(number_flags > 0){
	int total_cost = 0;
	total_cost = 900*number_flags;
	printf("\nThe final cost is: %d\n", total_cost);
[...]
```
