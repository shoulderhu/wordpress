:checkered_flag: picoCTF{look_in_image_13509d38}

## Solve
Can you help us find the flag in this [Meta-Material](https://2018shell.picoctf.com/static/9b8863e30054675ce78328df28c601db/2018.png)? You can also find the file in /problems/truly-an-artist_4_cdd9e325cf9bacd265b98a7fe336e840.

## Hints
Try looking beyond the image. Who created this?

## Solution
```
root@kali:~/Downloads# apt-get install libimage-exiftool-perl
==================== Output omitted ====================
root@kali:~/Downloads# exiftool 2018.png | grep picoCTF
Artist                          : picoCTF{look_in_image_13509d38}
```
