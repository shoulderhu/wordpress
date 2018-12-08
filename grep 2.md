:checkered_flag: picoCTF{grep_r_and_you_will_find_036bbb25}

## Solve
This one is a little bit harder. Can you find the flag in /problems/grep-2_4_06c2058761f24267033e7ca6ff9d9144/files on the shell server? Remember, grep is your friend.

## Hints
grep [tutorial](https://ryanstutorials.net/linuxtutorial/grep.php)

## Solution
```
shoulderhu@pico-2018-shell:~$ cd /problems/grep-2_4_06c2058761f24267033e7ca6ff9d9144/files
shoulderhu@pico-2018-shell:/problems/grep-2_4_06c2058761f24267033e7ca6ff9d9144/files$ ls
files0  files1  files2  files3  files4  files5  files6  files7  files8  files9
shoulderhu@pico-2018-shell:/problems/grep-2_4_06c2058761f24267033e7ca6ff9d9144/files$ find . -type f -exec cat {} \; | grep picoCTF
picoCTF{grep_r_and_you_will_find_036bbb25}
```
