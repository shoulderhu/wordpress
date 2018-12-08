:checkered_flag: picoCTF{J4y_s0n_d3rUUUULo_23fa6fa6}

## Solve
Our network administrator is having some trouble handling the tickets for all of of our incidents. Can you help him out by answering all the questions? Connect with `nc 2018shell.picoctf.com 63299`. [incidents.json](https://2018shell.picoctf.com/static/eddbe63bba72a01be6c7c5aba03807bd/incidents.json)

## Solution
```
root@kali:~/Downloads# nc 2018shell.picoctf.com 63299
You'll need to consult the file `incidents.json` to answer the following questions.

What is the most common source IP address? If there is more than one IP address that is the most common, you may give any of the most common ones.
135.171.87.112
Correct!

How many unique destination IP addresses were targeted by the source IP address 60.248.104.145?
1
Correct!

What is the number of unique destination ips a file is sent, on average? Needs to be correct to 2 decimal places.
1.42
Correct!

Great job. You've earned the flag: picoCTF{J4y_s0n_d3rUUUULo_23fa6fa6}
```

```
root@kali:~/Downloads# cat incidents.json | grep src_ip | sort | uniq -c
      2             "src_ip": "134.235.172.217",
      3             "src_ip": "135.171.87.112",
      3             "src_ip": "147.178.223.159",
      1             "src_ip": "60.248.104.145",
      1             "src_ip": "82.123.58.86",
root@kali:~/Downloads# cat incidents.json | grep -A 1 '"src_ip": "60.248.104.145"' | grep dst_ip | sort | uniq | wc -l
1
root@kali:~/Downloads# for file in $(cat incidents.json | grep file_hash | sort | uniq | cut -d ' ' -f 14); do cat incidents.json | grep -A 2 $file | grep dst_ip | sort | uniq | wc -l; done
2
2
2
1
1
1
1
root@kali:~/Downloads# echo "scale=2;(2+2+2+1+1+1+1)/7" | bc
1.42
```
