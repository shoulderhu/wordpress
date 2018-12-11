:checkered_flag: picoCTF{p1p1ng_1S_4_7h1ng_b6f5a788}

## Solve
Can you utlize stdin, stdout, and stderr to get the flag from this [program](https://2018shell.picoctf.com/static/0ca075b3119417f95a13236d763b4b50/in-out-error)? You can also find it in /problems/in-out-error_2_c33e2a987fbd0f75e78481b14bfd15f4 on the shell server

## Hints
Maybe you can split the stdout and stderr output?

## Solution
```
shoulderhu@pico-2018-shell:~$ cd /problems/in-out-error_2_c33e2a987fbd0f75e78481b14bfd15f4
shoulderhu@pico-2018-shell:/problems/in-out-error_2_c33e2a987fbd0f75e78481b14bfd15f4$ ./in-out-error 2>/tmp/shoulderhu/stderr.txt
Hey There!
If you want the flag you have to ask nicely for it.
Enter the phrase "Please may I have the flag?" into stdin and you shall receive.
Please may I have the flag?
Thank you for asking so nicely!
==================== Output omitted ====================
shoulderhu@pico-2018-shell:/problems/in-out-error_2_c33e2a987fbd0f75e78481b14bfd15f4$ cat /tmp/shoulderhu/stderr.txt | grep -o picoCTF{[^}]*} | uniq
picoCTF{p1p1ng_1S_4_7h1ng_b6f5a788}
```
