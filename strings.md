:checkered_flag: picoCTF{sTrIngS_sAVeS_Time_d3ffa29c}

## Solve
Can you find the [flag](https://2018shell.picoctf.com/static/a3d311b507256d5d9299c0e94dfc4fc5/strings) in this file without actually running it? You can also find the file in /problems/strings_4_40d221755b4a0b134c2a7a2e825ef95f on the shell server.

## Solution
```bash
root@kali:~/Downloads# strings strings | grep picoCTF
picoCTF{sTrIngS_sAVeS_Time_d3ffa29c}
```
