:checkered_flag: picoCTF{th3_5n4p_happ3n3d}

## Solve
There used to be a bunch of [animals](https://2018shell.picoctf.com/static/5d982298cdb725f9e23c6f25c8a37411/animals.dd) here, what did Dr. Xernon do to them?

## Hints
Some files have been deleted from the disk image, but are they really gone?

## Solution
```
root@kali:~/Downloads# foremost -t jpg,png -i animals.dd -v
Foremost version 1.5.7 by Jesse Kornblum, Kris Kendall, and Nick Mikus
Audit File

Foremost started at Sat Dec  8 21:37:17 2018
Invocation: foremost -t jpg,png -i animals.dd -v
Output directory: /root/Downloads/output
Configuration file: /etc/foremost.conf
Processing: animals.dd
|------------------------------------------------------------------
File: animals.dd
Start: Sat Dec  8 21:37:17 2018
Length: 10 MB (10485760 bytes)

Num	 Name (bs=512)	       Size	 File Offset	 Comment

0:	00000077.jpg 	     617 KB 	      39424
1:	00002277.jpg 	     380 KB 	    1165824
2:	00003041.jpg 	     248 KB 	    1556992
3:	00003541.jpg 	     314 KB 	    1812992
4:	00004173.jpg 	     458 KB 	    2136576
5:	00005093.jpg 	     383 KB 	    2607616
6:	00005861.jpg 	      39 KB 	    3000832
*|
Finish: Sat Dec  8 21:37:17 2018

7 FILES EXTRACTED

jpg:= 7
------------------------------------------------------------------

Foremost finished at Sat Dec  8 21:37:17 2018
```

![1](https://raw.githubusercontent.com/shoulderhu/wordpress/master/picoCTF/2018/Forensics/Recovering%20From%20the%20Snap/output/jpg/00005861.jpg)
