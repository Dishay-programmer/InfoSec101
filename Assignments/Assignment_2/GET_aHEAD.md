# PicoGym Web Exploitation Writeup


Author: [Dishay Mehta](https://github.com/Dishay952) 

Challenge Page: [Get aHEAD](http://mercury.picoctf.net:34561/)

## Walkthrough
So seeing the source code of the page we get to know 2 methods `GET` and `POST` in http exploit.Now looking at the hint and searching for another method `HEAD` which is used to fetch a result similar to GET but with no response body i.e. can be used to acess internal pages.
using Burp Suite we can modify the requests and look at the responses.

## Flag
`picoCTF{r3j3ct_th3_du4l1ty_8f878508}`

## Useful resources (if any)
