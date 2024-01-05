>[!danger]- Answer
> poctf{uwsp_533k_4nd_y3_5h411_f1nd}
- e, N, and C, hmmmmmmmmm sounds familiar ([[RSA]])
- since the N is very small, use online factorizer thingy
- factorization of 34034827 is 5807 \* 5861
- those are our p & q 
- using tool using [[RSA]]#2, I got that the private key was 202559
- with that website, input the cipher text and it will decode it into ascii i think which u can convert to the letters (may need to remove spaces and replace with underscore)