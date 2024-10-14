# MakeNotes
Makefiles notes

# TODO DROPDOWNS
- [ ] USERMODE
- [ ] KERNELMODE


## makefile with filename `Makefile`
```Makefile
CC = gcc
CFLAGS = -Wall

all: hello

hello: hello.o
    $(CC) $(CFLAGS) -o hello hello.o

hello.o: hello.c
    $(CC) $(CFLAGS) -c hello.c

clean:
    rm -f hello hello.o
```

## C file with filename `hello.c`
```c
#include <stdio.h>
int main() {
    printf("Hello, World!\n");
    return 0;
}
```

## Output
```sh
[user@fedora CODE]$ ls -1la
  total 8
  drwxr-xr-x.  2 user user  80 Oct 14 20:53 .
  drwxrwxrwt. 14 root root 300 Oct 14 20:15 ..
  -rw-r--r--.  1 user user 160 Oct 14 12:16 Makefile
  -rw-r--r--.  1 user user  81 Oct 14 12:06 hello.c


[user@fedora CODE]$ make
    gcc -Wall -c hello.c
    gcc -Wall -o hello hello.o

[user@fedora CODE]$ ls -1la
  total 32
  drwxr-xr-x.  2 user user   120 Oct 14 20:53 .
  drwxrwxrwt. 14 root root   300 Oct 14 20:53 ..
  -rw-r--r--.  1 user user   160 Oct 14 12:16 Makefile
  -rwxr-xr-x.  1 user user 16680 Oct 14 20:53 hello
  -rw-r--r--.  1 user user    81 Oct 14 12:06 hello.c
  -rw-r--r--.  1 user user  1512 Oct 14 20:53 hello.o

[user@fedora CODE]$ ./hello 
    Hello, World!
```

## References / Sources & Further Readings
- This ^ Hello world project BUT in KERNELMODE [Loadable Kernel Modules(LKM)](https://gist.github.com/loneicewolf/226e3e20e6041d12a63a5e833ebb0503?permalink_comment_id=4452381#gistcomment-4452381)
- 
