:checkered_flag: picoCTF{extensions_are_a_lie}

## Solve
Hmm for some reason I can't open this [PNG](https://2018shell.picoctf.com/static/0fde1a3e09824365348827194db9cdde/flag.png)? Any ideas?

## Hints
How do operating systems know what kind of file it is? (It's not just the ending!)

## Solution
```bash
root@kali:~/Downloads# xxd flag.png | head -n 1
00000000: ffd8 ffe0 0010 4a46 4946 0001 0101 004b  ......JFIF.....K
root@kali:~/Downloads# mv flag.png flag.jpg
```

![1](https://www.dropbox.com/s/6gec4v8txac0wqc/Forensics-Warmup-2.jpg?raw=1)
