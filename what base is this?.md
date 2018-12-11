:checkered_flag: picoCTF{delusions_about_finding_values_602fd280}

## Solve
To be successful on your mission, you must be able read data represented in different ways, such as hexadecimal or binary. Can you get the flag from this program to prove you are ready? Connect with `nc 2018shell.picoctf.com 14390`.

## Hints
I hear python is a good means (among many) to convert things.

## Solution
```python
from pwnlib.tubes import remote

def recv_until(delims):
    recv = nc.recvuntil(delims).decode().split("\n")
    for line in recv:
        print(line)
    return recv

def base2(recv):
    recv = recv[-3].split(" ")
    word = ""
    for i in recv[4 : len(recv) - 3]:
        word += chr(int(i, 2))
    print(word)
    nc.sendline(word)

def base16(recv):
    recv = recv[1].split(" ")[4]
    word = ""
    for i in range(0, len(recv), 2):
        word += chr(int(recv[i : i + 2], 16))
    print(word)
    nc.sendline(word)

def base8(recv):
    recv = recv[1].split(" ")
    word = ""
    for i in recv[5 : len(recv) - 3]:
        word += chr(int(i, 8))
    print(word)
    nc.sendline(word)

def recv_repeat():
    for line in nc.recvrepeat().decode().split("\n"):
        print(line)

nc = remote.remote("2018shell.picoctf.com", 14390)
base2(recv_until("Input:"))
base16(recv_until("Input:"))
base8(recv_until("Input:"))
recv_repeat()
nc.close()

'''
We are going to start at the very beginning and make sure you understand how data is stored.
lamppost
Please give me the 01101100 01100001 01101101 01110000 01110000 01101111 01110011 01110100 as a word.
To make things interesting, you have 30 seconds.
Input:
lamppost
Please give me the 67696d70 as a word.
Input:
gimp
Please give me the  164 157 170 151 143 as a word.
Input:
toxic
You got it! You're super quick!
Flag: picoCTF{delusions_about_finding_values_602fd280}
'''
```
