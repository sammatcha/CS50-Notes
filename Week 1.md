First program in C:
```
#include <stdio.h>

int main(void)
{
  printf("hello, world \n");
}
```
Command to compile program:
```
make hello
```

#### Note:
##### `make` used to build executable programs & libraries from source code
##### - a new file called `hello` is made

Run ```./hello``` <br>
#### Note: <br>
##### `(.)` says to go into current folder
##### `/hello` means run the program called "hello" in this current folder

Delete file:
``` 
rm hello
```
##### `rm` is for remove

list files in current folder:
```
ls
```
<img width="268" alt="image" src="https://user-images.githubusercontent.com/60681017/196064028-600f55d9-5e56-4c76-9ead-e83a6fcd3b28.png">

- use double quotes, `" "` for strings
- end with `;`

``` 
answer = get_string("what's your name?");
```
- `answer` is return value
- `get_string` is function

#### Note: when changing the string in the print, will have to run `make hello` to compile again

## Program to get string from user:
```
#include <stdio.h>

int main(void)
{
    string answer = get_string("What's your name? ");
    printf("hello, answer\n");
}
```
- compile with `make hello`
- we get errors, look down at errors section to find out why
- **library** is loaded on top, aka **header file** `include < >`

## Errors:
```
#include <stdio.h>
int main(void)
{
  printf("hello, world
  ");
  }
  ```
  - the closing `"` needs to be on the same line

Getting string from user error
`hello.c:5:5: error: use of undeclared identifier 'string'; did you mean 'stdin'?
    string answer = get_string("What's your name? ");`
    - string is not defined. Need to load libraries

```
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    string answer = get_string("What's your name? ");
    printf("hello, answer\n");
}
```
outputs:
`Whats your name? Samantha `
`hello, answer`
- not quite right. 

more is needed to the syntax:
```
printf("hello, %s\n", answer);
```
- `%s` is a placeholder saying put a string here

## Linux commands:
- `cd` changing current directory (folder)
- `cp` copying files & dir
- `ls` listing files in a dir
- `mkdir` making a dir
- `mv` moving(renaming) files & dir
- `rm` removing (deleting) files
- `rmdir` removing (deleting) directories

1. created directory called pset1 and pset2
2. cd into pset1
3. ls pset1
4. make a new directory inside pset1 called mario
5. create new file called mario.c
```
code mario.c
```
- creates a new file called mario.c

going back 2 levels with `..`
example:
`cd ..` , `cd../..`, `cd`

`.` means current directory

# Types, format codes, operators

