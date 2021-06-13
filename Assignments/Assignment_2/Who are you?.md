# PicoGym Web Exploitation Writeup


Author: [Dishay Mehta](https://github.com/Dishay952) 

Challenge Page: [Who are you?](http://mercury.picoctf.net:46199/)

## Walkthrough
Opening Burpsuite and changing the `User-Agent` to "picobrowser". Then after a ton of search I came across a HTTP Header named `Referer` which has the following property - the address of the previous web page from which a link to the currently requested page was followed . Then using `Date` , I changed the year to 2018. Then using `DNT: 1` we can stop being tracked. Using `X-Forwarded-For` I fooled the website into thinking that user is from Sweden by inputting its IP address(31.15.32.0). Lastly editing the `Accept-Language` to sv we can speak Swedish :).

## Flag
`picoCTF{http_h34d3rs_v3ry_c0Ol_much_w0w_8d5d8d77}`

## Useful resources (if any)
