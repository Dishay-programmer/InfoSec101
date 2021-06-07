# Bandit Level 14 to 15 Writeup

Author: [Dishay Mehta](https://github.com/Dishay-programmer)

Problem Page: [bandit15](https://overthewire.org/wargames/bandit/bandit15.html)

## List of Commands Used
```
ls - list files in a directory
nc - used for just about anything under the sun involving TCP or UDP .i.e in simple language can be used to transfer data from one host to the post of other
```

## Walkthrough
So I did bandit level 13 inorder to find where exactly is the password for bandit14 stored as this level required me to find the exact location of that file and basically transfer it to the port `30000` of hostname `localhost`.Then I searched about `telnet` and `nc` on google and with proper googling came across a site which made me understand what exactly the `nc` command did. I'll provide the link for the same-[nc command](https://linux.die.net/man/1/nc) :wink:

## Password
`BfMYroe26WYalil77FoDi9qh59eK5xNr`

## Bash/Python script to automate the process
```
ssh bandit14@bandit.labs.overthewire.org -p 2220 "nc localhost 30000 < /etc/bandit_pass/bandit14"
```