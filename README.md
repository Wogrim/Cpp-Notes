# Getting Started

C++ is a compiled language; you must install a compiler to change your code into an executable.

The "standard" compiler to get is the **g++** compiler from the GNU Compiler Collection.

To get it on Windows
- install [MSYS2](https://www.msys2.org/)
- open the MSYS2 MINGW64 environment (the start menu shortcut)
- `pacman -S mingw-w64-x86_64-gcc` to install the package with the compiler
- add `C:\msys64\mingw64\bin` to PATH so that Windows can find the g++ command
- in powershell (or other terminal) you should now be able to use `g++ --version` to verify installation

create a **hello_world.cpp** file somewhere and put in
```
//for cout
#include <iostream>

//so you can just say cout instead of std::cout
using namespace std;

//program entry point
int main(){
    //print some stuff
    cout << "Helloooooo." << endl;

    return 0;
}

```

to compile it (in terminal in same folder)
```
g++ hello_world.cpp -o hello_world.exe
```

if you try to run it normally, it will pop up a window and disappear instantly because the program ends fast

so run it in the terminal via
```
.\hello_world
```

# Funky Features of C++

- compiled to assembly for specific hardware; needs to be compiled differently for special systems
- arrays and other collections are homogeneous; they only allow one data type
- able to overload operators to work with whatever data types you like (even your own classes)

# Data Types and Variables

- variables are explicitly typed
  - you must declare variables with a type before you can use them
- variables are statically typed
  - you can't change the type of a variable after you declare it
- you can *initialize* a variable by ASSIGNing a value to it when it is declared
  - `int health = 100;`
- variables can be declared **const** which prevents them from being changed (recommended)
  - specifically you'll get a compiler error if you try to change it
- variable names ("identifiers") can contain letters, underscores, digits, can't start with a digit
  - convention: don't start with uppercase letter
- universal (more or less) operators, which result in a boolean
- `x == y`
  - EQUALS
- `x != y`
  - NOT EQUALS

## primitives

- some different types can be implicitly cast to each other

### numbers

integer types are whole numbers, which can be preceded by **unsigned** to not allow negatives
- **char** is 8-bit, but you can assign individual characters
  - `char c = 'a';`
  - -127 to 128 or unsigned is 0 to 255
- **int** is 32-bit
  - `int i = 0;`
  - -2 billion to + 2 billion, or unsigned is 0 to 4 billion
- **long** is 64-bit (use when int is too small)
  - `long x = 50000000L * 10000L;
  - L at the end of literals to treat as long to avoid int overflow
- division with integer types does integer division
  - `int wholes = 100 / 17;`
- modular division to get the remainder
  - `int remainder = 100 % 17;`

float types are fractional numbers
- **float** is lower-precision
  - `float f = 5f / 3;`
  - **f** at the end of literals for it to be treated as float instead of int
- **double** is higher-precision

incrementing and decrementing a number variable
- `x++` or `++x`
  - these are expressions to increase x by 1, which can be used as part of a larger statement
    - the former returns the pre-incremented value of x, the latter the post-incremented value
- `x--` or `--x`
  - similar for decreasing by 1
- `x += 5;` and `x -= 5;`
  - shorthand for `x = x + 5;` and `x = x - 5;` respectively
  - there is also *= /= %=

comparison operators work on numbers and result in a boolean
- `x > 5`
  - GREATER THAN
- `x >= 5`
  - GREATER THAN OR EQUAL TO
- `x < 5`
  - LESS THAN
- `x <= 5`
  - LESS THAN OR EQUAL TO

### booleans

booleans are true or false values, requiring boo

```
bool has_money = false;
bool has_time = true;
```

the following operators work on booleans (and result in a boolean)
- `! has_money`
  - NOT
- `has_money && has_time`
  - AND
- `has_money || has_time`
  - OR

universal (more or less) operators that result in a boolean
- `x == y`
  - EQUALS
- `x != y`
  - NOT EQUALS

### strings

- strings are sequences of characters, but they're really just objects underneath

