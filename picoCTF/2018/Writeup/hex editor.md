:checkered_flag: picoCTF{and_thats_how_u_edit_hex_kittos_dF817ec5}

## Solve
This [cat](https://2018shell.picoctf.com/static/1b3f7771b439137d8a9e5cf07d8e3e2d/hex_editor.jpg) has a secret to teach you. You can also find the file in /problems/hex-editor_4_0a7282b29fa47d68c3e2917a5a0d726b on the shell server.

## Hints
What is a hex editor?   
[xxd](http://linuxcommand.org/man_pages/xxd1.html)  
[hexedit](http://linuxcommand.org/man_pages/hexedit1.html)  
[bvi](http://manpages.ubuntu.com/manpages/natty/man1/bvi.1.html)  

## Solution
```
root@kali:~/Downloads# xxd hex_editor.jpg | tail -n 5
0012930: 8a00 ffd9 596f 7572 2066 6c61 6720 6973  ....Your flag is
0012940: 3a20 2270 6963 6f43 5446 7b61 6e64 5f74  : "picoCTF{and_t
0012950: 6861 7473 5f68 6f77 5f75 5f65 6469 745f  hats_how_u_edit_
0012960: 6865 785f 6b69 7474 6f73 5f64 4638 3137  hex_kittos_dF817
0012970: 6563 357d 220a                           ec5}".
```
