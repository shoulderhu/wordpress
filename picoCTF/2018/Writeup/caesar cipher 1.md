:checkered_flag: picoCTF{justagoodoldcaesarcipherobyujeez}

## Solve
This is one of the older ciphers in the books, can you decrypt the [message](https://2018shell.picoctf.com/static/6b5626c0736d9090f5d98de74eec4543/ciphertext)? You can find the ciphertext in /problems/caesar-cipher-1_0_931ac10f43e4d2ee03d76f6914a07507 on the shell server.

## Hints
caesar cipher [tutorial](https://learncryptography.com/classical-encryption/caesar-cipher)

## Solution
```
root@kali:~/Downloads# prev=a
root@kali:~/Downloads# for letter in {b..z}; do echo yjhipvddsdasrpthpgrxewtgdqnjytto | tr a-z $letter-za-$prev; prev=$letter; done
zkijqweetebtsquiqhsyfxuherokzuup
aljkrxffufcutrvjritzgyvifsplavvq
bmklsyggvgdvuswksjuahzwjgtqmbwwr
cnlmtzhhwhewvtxltkvbiaxkhurncxxs
domnuaiixifxwuymulwcjbylivsodyyt
epnovbjjyjgyxvznvmxdkczmjwtpezzu
fqopwckkzkhzywaownyeldankxuqfaav
grpqxdllaliazxbpxozfmebolyvrgbbw
hsqryemmbmjbaycqypagnfcpmzwshccx
itrszfnncnkcbzdrzqbhogdqnaxtiddy
justagoodoldcaesarcipherobyujeez
kvtubhppepmedbftbsdjqifspczvkffa
lwuvciqqfqnfecguctekrjgtqdawlggb
mxvwdjrrgrogfdhvduflskhurebxmhhc
nywxeksshsphgeiwevgmtlivsfcyniid
ozxyflttitqihfjxfwhnumjwtgdzojje
payzgmuujurjigkygxiovnkxuheapkkf
qbzahnvvkvskjhlzhyjpwolyvifbqllg
rcabiowwlwtlkimaizkqxpmzwjgcrmmh
sdbcjpxxmxumljnbjalryqnaxkhdsnni
tecdkqyynyvnmkockbmszrobylietooj
ufdelrzzozwonlpdlcntaspczmjfuppk
vgefmsaapaxpomqemdoubtqdankgvqql
whfgntbbqbyqpnrfnepvcurebolhwrrm
xighouccrczrqosgofqwdvsfcpmixssn
```
