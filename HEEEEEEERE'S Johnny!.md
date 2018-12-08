:checkered_flag: picoCTF{J0hn_1$_R1pp3d_1b25af80}

## Solve
Okay, so we found some important looking files on a linux computer. Maybe they can be used to get a password to the process. Connect with `nc 2018shell.picoctf.com 40157`. Files can be found here: [passwd](https://2018shell.picoctf.com/static/7a017af70c0b86ab002896616376499e/passwd) [shadow](https://2018shell.picoctf.com/static/7a017af70c0b86ab002896616376499e/shadow).

## Solution
```
root@kali:~/Downloads# cat shadow
root:$6$q7xpw/2.$la4KiUz87ohdszbOVoIopy2VTwm/5jEXvWSdWynh0CnP5T.MnJfVNCzp3IfJMHUNuBhr1ewcYd8PyeKHqHQoe.:17770:0:99999:7:::
root@kali:~/Downloads# john shadow
Created directory: /root/.john
Warning: detected hash type "sha512crypt", but the string is also recognized as "crypt"
Use the "--format=crypt" option to force loading these as that type instead
Using default input encoding: UTF-8
Loaded 1 password hash (sha512crypt, crypt(3) $6$ [SHA512 128/128 SSE2 2x])
Press 'q' or Ctrl-C to abort, almost any other key for status
kissme           (root)
1g 0:00:00:08 DONE 2/3 (2018-11-23 17:11) 0.1191g/s 537.6p/s 537.6c/s 537.6C/s keller..mermaid
Use the "--show" option to display all of the cracked passwords reliably
Session completed
root@kali:~/Downloads# nc 2018shell.picoctf.com 40157
Username: root
Password: kissme
picoCTF{J0hn_1$_R1pp3d_1b25af80}
```
