:checkered_flag: picoCTF{j0hn_c3na_paparapaaaaaaa_paparapaaaaaa_22f627d9}

## Solve
'...reading transmission... Y.O.U. .C.A.N.'.T. .S.E.E. .M.E. ...transmission ended...' Maybe something lies in /problems/you-can-t-see-me_4_8bd1412e56df49a3c3757ebeb7ead77f.

## Hints 
What command can see/read files?  
What's in the manual page of ls?

## Solution
```
shoulderhu@pico-2018-shell:~$ cd /problems/you-can-t-see-me_4_8bd1412e56df49a3c3757ebeb7ead77f
shoulderhu@pico-2018-shell:/problems/you-can-t-see-me_4_8bd1412e56df49a3c3757ebeb7ead77f$ ls -a
.  .    ..
shoulderhu@pico-2018-shell:/problems/you-can-t-see-me_4_8bd1412e56df49a3c3757ebeb7ead77f$ find -type f -exec cat {} \;
picoCTF{j0hn_c3na_paparapaaaaaaa_paparapaaaaaa_22f627d9}
shoulderhu@pico-2018-shell:/problems/you-can-t-see-me_4_8bd1412e56df49a3c3757ebeb7ead77f$ cat .* 2>/dev/null
picoCTF{j0hn_c3na_paparapaaaaaaa_paparapaaaaaa_22f627d9}
```
