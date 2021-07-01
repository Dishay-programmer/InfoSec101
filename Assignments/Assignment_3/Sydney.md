# MicroCTF Writeup


Author: [Dishay Mehta](https://github.com/Dishay952/InfoSec101/tree/main/Assignments/Assignment_3) 

Level: Sydney

## Walkthrough
Going through the main function we can see that if r15 after the function call is non zero 
then we can unlock the door.
Inspecting `check_password`
```
448a <check_password>
448a:  bf90 755d 0000 cmp	#0x5d75, 0x0(r15)
4490:  0d20           jnz	$+0x1c
4492:  bf90 5423 0200 cmp	#0x2354, 0x2(r15)
4498:  0920           jnz	$+0x14
449a:  bf90 2f59 0400 cmp	#0x592f, 0x4(r15)
44a0:  0520           jne	#0x44ac <check_password+0x22>
44a2:  1e43           mov	#0x1, r14
44a4:  bf90 604a 0600 cmp	#0x4a60, 0x6(r15)
44aa:  0124           jeq	#0x44ae <check_password+0x24>
44ac:  0e43           clr	r14
44ae:  0f4e           mov	r14, r15
44b0:  3041           ret
```
Clearly we can see that 
-first 2 bytes are being compared to 0x5d75
-next 2 bytes are being compared to 0x2354
-next 2 bytes are being compared to 0x592f
-last 2 bytes are being compared to 0x4a60
so in order to avoid the line
```44ac:  0e43           clr	r14```
we need all these conditions to be true.
hence we ned to input the password (as hex) `5d752354592f4a60`.
But in since assembly little endian storage is used we must reverse the alternate bytes.
Hence the payload in hex should look like 
`5d7554232f59604a`
This will unlock the door.
## Password
`5d7554232f59604a`