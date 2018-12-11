:checkered_flag: picoCTF{th4t_w4s_s1mpL3}

## Solve
Can you decode the following string `dGg0dF93NHNfczFtcEwz` from base64 format to ASCII?

## Solution
```
root@kali:~# python3
Python 3.6.7 (default, Oct 21 2018, 08:08:16)
[GCC 8.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import base64
>>> base64.b64decode('dGg0dF93NHNfczFtcEwz')
b'th4t_w4s_s1mpL3'
```
