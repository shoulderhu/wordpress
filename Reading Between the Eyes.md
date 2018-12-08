:checkered_flag: picoCTF{r34d1ng_b37w33n_7h3_by73s}

## Solve
Stego-Saurus hid a message for you in this [image](https://2018shell.picoctf.com/static/3e423171eed198e8425524a1b052869b/husky.png), can you retreive it?

## Solution
```python
import cv2 as cv

img = cv.imread("husky.png", 1)
lsb = "0b"

for i in range(0, img.shape[0]):
    for j in range(0, img.shape[1]):
        lsb += str(img[i, j][2] % 2)
        lsb += str(img[i, j][1] % 2)
        lsb += str(img[i, j][0] % 2)
        print(i, j)

lsb = int(lsb, 2)
message = lsb.to_bytes((lsb.bit_length() + 7) // 8, 'big').decode()

with open("husky2.txt", "w") as txt:
    txt.write(message)
```

```
root@kali:/tmp/pycharm_project_859# cat husky.txt
picoCTF{r34d1ng_b37w33n_7h3_by73s}
```
