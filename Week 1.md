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
## Data Types
- `bool` (Boolean): True/False
- `char`: single character like `a` or `2`
- `double`: floating-pt value with more digits than a `float`, more precision
- `float`: floating-pt value or real number with a decimal value
- `int`: integers up to a certain size or number of bits
- `long`: bigger integer, can count higher than `int`
- `string`

## format codes
printing different types of data `printf`
- `%c` char
- `%f` floats/ doubles
- `%i` ints
- `%li` long integers
- `%s` string

## Operators
- `+` addition
- `-` subtraction
- `*` multiplication
- `/` division
- `%` remainder

# Variables, syntactic sugar
counter in C:
```
int counter = 0;
```
incrementing counter:
```
counter = counter + 1;
```
a more succinct way to write this is :
```
counter +=1;
```
or 
```
counter++;
```
# Calcuations
calculator.c
```
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    int x = get_int("x: ");
    int y = get_int("y: ");
    printf("%i\n", x + y);
}
```
## Compiling
[Follow the CS50 Docs](https://cs50.readthedocs.io/libraries/cs50/c/)
- I followed From Source instructions and the environment variables
I was not able to compile with the `make` command but what worked for me was:
```
clang -o calculator calculator.c -lcs50
```
```
./calculator
```
run the code again w/ `./calculator` <br>
`x =1000000000` <br>
`y = 1000000000` <br>
`2000000000` <br>
run the code again <br>
`x = 2000000000` <br>
`y = 2000000000` <br>
`-294967296`
**why?**
*ran out of bits* the data types use finite amount of bits
`int` can count up to -2B to 2B <br>
change the data type to `long`
```
int main(void)
{
    long x = get_long("x: ");
    long y = get_long("y: ");
    printf ("%li\n", x+y);
}
```
compile code again and run again should result in previous calculation of 2B+2B = 4B
## Condition & Boolean
# if 
```
if (x < y){
    printf("x is less than y");
}
```
# if / else
```
if (x < y)
{
    printf("x is less than y\n");
}
else
{
    printf("x is not less than y\n");
}
```
# else if
```
if (x < y)
{
    printf("x is less than y\n");
}
else if (x > y)
{
    printf("x is greater than y\n");
}
else (x == y)
{
    printf("x is equal to y\n");
}
```
### agree.c 
//asking user if they agree
```
//program to agree or not to agree
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    // Prompt user to agree
    char c = get_char("Do you agree? ");

    // Check whether agreed
    if (c == 'Y' || c == 'y')
    {
        printf("Cool\n");
    }
    else if (c == 'N' || c == 'n')
    {
        printf("Why not?\n");
    }
}
```

`||` means *or*
`&&` means *and*
`char` is surrounded by `' '` (single quotes)
- `string` uses `" "` (double quotes)

## Loops
while loop repeats while condition is true
program to meow 3x:
```
//program to meow 3x using while loop

int main (void)
{
// initialize variable
    int i = 0;
    while (i<3) //ask question
    {
        printf("nya\n");
        i+=1; // increment counter
    }
}
```
can also use a for loop:
```
//program to meow 3x using for loop

#include <stdio.h>
int main (void)
{
    for (int i = 0; i < 3; i++)
    {
        printf("nya\n");
    }
    
}
```
differences between the two loops is that initializing variables outside of the loop will be applied to rest of code

## Creating our own function
*return type* function (*input)
example: 
``` void nya (void)
```
void means it doesnt return anything and it doesnt take inputs/ arguments <br>
call the function <br>

if you move the created function on the bottom, there will be errors because the compiler reads from top to bottom. <br>
declare the function with a **prototype** on top to tell the compiler function will be defined later <br>
example:
```
void nya (void);
int ...{ }
for ... 
{ }
void nya(void)
{
printf("nya\n");
}
```
## Note:
- get_string and those related functions are part of the cs50 library `<cs50.h>`

## Imprecision, Overflow
using `calculator.c` and asking for 50 decimal places with `% .50f` leads to **floating- point imprecision** which is inability for computers to represent all real numbers 100% precisely.
using calculator.c <br>
```
int main(void)
{
    int x = get_long("x: ");
    int y = get_long("y: ");
    float z = (float) x / (float)y;
    printf ("%.50f\n", z);

```
x and y are `int` types and z is a `float`. Convert int type to float for x and or y to get an answer closer to the actual answer but there is still imprecision. <br>

use `math.h` library to use **round** function
in a program to convert dollar amount to pennies, use round function to get a correct penny amount for $4.20
- when we didnt use round, the program resulted in 419 pennies for $4.20 

