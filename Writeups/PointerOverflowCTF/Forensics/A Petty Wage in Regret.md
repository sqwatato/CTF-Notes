>[!danger] Answer
>poctf{uwsp_7h3_w0rld_h4d_17_f1257}
- first i tried using [[strings]] on the image, but nothing stood out
- i then used [[exiftool]] and found a user comment which looked suspicious
- so i put it into [[CyberChef]] and used magic and it was in hex for the first part of the flag
- the decoded message also said this was half of the flag
- if you look very closely to image, you can see some sort of distortion, with some looking like numbers
- i uploaded it to [[FotoForensics]] and used the ELA tool to see the compression levels or smth (checks if the pixels around it are similar color/brightness) to make sussy stuff pop out
- and there it is part 2 of the flag is visible in the image (combine with underscore)