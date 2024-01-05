>[!danger]- Answer
> poctf(uwsp_w31c0m3_70_7h3_94m3}
- Download the corrupt pdf file, you can't open it, so we must look at its data
- i used [[strings]] `strings DF1.pdf` and got the encrypted flag 
	- `poctf(uwsp_77333163306D335F37305F3768335F39346D33}`
- then taking the number inside the flag, i inputted into [[CyberChef]] and used magic to get the decoded part of the flag