:checkered_flag: picoCTF{who_n33ds_p4ssw0rds_38dj21}

## Solve
As nice as it is to use our webshell, sometimes its helpful to connect directly to our machine. To do so, please add your own public key to ~/.ssh/authorized_keys, using the webshell. The flag is in the ssh banner which will be displayed when you login remotely with ssh to with your username.

## Hints
key generation [tutorial](https://confluence.atlassian.com/bitbucketserver/creating-ssh-keys-776639788.html)  
We also have an expert demonstrator to help you along. [link](https://www.youtube.com/watch?v=3CN65ccfllU&list=PLJ_vkrXdcgH-lYlRV8O-kef2zWvoy79yP&index=4)

## Solution
```
root@kali:~$ ssh-keygen 
Generating public/private rsa key pair.
Enter file in which to save the key (/root/.ssh/id_rsa): 
Created directory '/root/.ssh'.
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /root/.ssh/id_rsa.
Your public key has been saved in /root/.ssh/id_rsa.pub.
The key fingerprint is:
==================== Output omitted ====================
The key's randomart image is:
==================== Output omitted ====================
```

```
shoulderhu@pico-2018-shell:~$ mkdir .ssh                              
shoulderhu@pico-2018-shell:~$ echo "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCzGe5IkLCkH6UTVYnPq7sIFEpq4D1X2Fl3d9OT/EyuzEL931aHrH9PK/S7lKNlnU6c7fudCWEhYtN/i1ZAK4kUaRresvYiXM23dXiPvimhjrzUbxySaifKIkAoYNFPdtHa26MFTeca6+K+b6Mzzs4hXhnQhBQwMi5Q4XORnrhVpTq1hE1dEvDKJe+BwfzEDyn7ikN2gOFifpF8TRMFlhWC5ZP5nVdKko8vEfjC8VOyNvH0RlTix73OcYO/6nsqR14AeuTsOydHH86zY1AvdIYqhYy414Sd3UdfPSaTY8wXwU7rYnMSu6awz1uYaBRksp0gL6eFfe9uFfWl1D0kkgE3 root@kali" > ~/.ssh/authorized_keys  
root@kali:~# ssh shoulderhu@2018shell.picoctf.com
The authenticity of host '2018shell.picoctf.com (18.188.57.214)' can't be established.
ECDSA key fingerprint is SHA256:cLYL/h/zTqqapwkOtHLvuBv/ire4/UakBVvpUpBNqII.
ECDSA key fingerprint is MD5:6d:36:6f:b3:d6:25:e0:ad:b1:86:73:b0:0b:a3:32:11.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added '2018shell.picoctf.com' (ECDSA) to the list of known hosts.
picoCTF{who_n33ds_p4ssw0rds_38dj21}
```
