<link rel="stylesheet" type="text/css" href="README.css">

# C-Tutorial
**C as a Mother Language**
>- C language is considered as the mother language of all the modern programming languages, because most of the compilers, JVMs, Kernels, etc. are written in C language.
>- And most of the programming languages follow C syntax, like C++, Java, C# etc.
<hr>
<b>C Program Example:</b> <br>

```C
// File: main.c
#include <stdio.h>                  // standard input output library
int main() {                        // main() function is the entry point of every program.
  printf("Hello C Programming\n");
  return 0;
}
```
<hr>
<b> Compilation Process in C:</b><br>

> The compilation is a process of converting the `source code` into `object code`. It is done with the help of the **compiler**. <br>
The compiler checks the *source code* for syntactical or structural errors, and if the source code is error-free, then it generates the *object code*.<br>
The compilation process can be divided into four steps, i.e.,
>- Pre-processing 
>- Compiling 
>- Assembling 
>- Linking.

	source code -> [Preprocessor] -> expanded code  -> [Compiler] -> assembly code  -> [Assembler] -> object code -> [Linker] with other object files and libraries -> executable code
	
	hello.c     -> [Preprocessor] -> hello.i        -> [compiler] -> hello.s        -> [Assembler] -> hello.obj   -> [Linker] -> hello.exe -> [Loader] -> execution
<hr>
