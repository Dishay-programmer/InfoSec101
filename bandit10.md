# Bandit Level 10 to 11 Writeup

Author: [Dishay Mehta](https://github.com/Dishay-programmer)

Problem Page: [bandit11](https://overthewire.org/wargames/bandit/bandit11.html)

## List of Commands Used
```
ls - list files in a directory
base64 - base64 encode/decode data and print to standard output
```

## Walkthrough
So firstly i searched the command base64 using `man base64` then found out about the `-d` flag of it which is use to decode the data of a file named `data.txt` which was base64 encoded and et voilà :smiley:

## Password
`IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR`

## Bash/Python script to automate the process
```
ssh bandit10@bandit.labs.overthewire.org -p 2220 "base64 -d data.txt"
```

## Suggested modifications [Optional]
The given file should have been hex dump encoded and decompressed along with many variants of b2zip,gzip, TAR archive to increase the difficulty.