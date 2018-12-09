:checkered_flag: picoCTF{delusions_about_finding_values_602fd280}

## Solve
To be successful on your mission, you must be able read data represented in different ways, such as hexadecimal or binary. Can you get the flag from this program to prove you are ready? Connect with `nc 2018shell.picoctf.com 14390`.

## Hints
I hear python is a good means (among many) to convert things.

## Solution
```
root@kali:~/Downloads# nc 2018shell.picoctf.com 14390
We are going to start at the very beginning and make sure you understand how data is stored.
turtle
Please give me the 01110100 01110101 01110010 01110100 01101100 01100101 as a word.
To make things interesting, you have 30 seconds.
Input:
turtle
Please give me the 74657374 as a word.
Input:
test
Please give me the  163 171 155 142 157 154 as a word.
Input:
symbol
You got it! You're super quick!
Flag: picoCTF{delusions_about_finding_values_602fd280}
```

```python
Bin = "01110100 01110101 01110010 01110100 01101100 01100101"
Hex = "74657374"
Dec = "163 171 155 142 157 154"
word1 = ""
word2 = ""
word3 = ""

for i in Bin.split(" "):
    word1 += chr(int(i, 2))
print(word1)

for i in range(0, len(Hex), 2):
    word2 += chr(int(Hex[i:i + 2], 16))
print(word2)

for i in Dec.split(" "):
    word3 += chr(int(i, 8))
print(word3)
```
