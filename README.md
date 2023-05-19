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
	
	hello.c     -> [Preprocessor] -> hello.i        -> [Compiler] -> hello.s        -> [Assembler] -> hello.obj   -> [Linker] -> hello.exe -> [Loader] -> execution
<hr>



***printf() & scanf() in C***

>Syntax For printf()
``` C
printf("format string", argument_list);
%d - Integer
%c - Character
%s - String
%f - Float
etc.
```

>Syntax For scanf()
	
``` C
scanf("format string", argument_list);
```

> Example:

``` C
#include <stdio.h>
int main() {
	int number;
	printf("enter a number: ");
	scanf("%d", &number);
	printf("cube of the number is: %d", number*number*number);
	return 0;
}
``` 


<hr>

***Variable in C***

>Syntax to declare a variable:

	data_type variable_list;

>Examples:

``` C
int a;
float b;
char c;
int x=10, y=20;
float f = 20.8;
char ch = 'A';
```

>Types of variables:
>- Local Variable
>- Global Variable
>- Static Variable
>- Automatic Variable
>>All variables in C that are declared inside the block, are automatic variables *by default*.  We can also explicitly declare an automatic variable using `auto` keyword.	
>- External Variable
>>External variables are also a part of global variables.
>>We can share a variable in multiple C files by using an external variable.
	
>Examples:

``` C
// File: file1.c
#include "file.h"
#include <stdio.h>
int global_variable = 100;
void function1() {
	int local_variable = 10;
	static int static_variable = 1;
	auto int automatic_variable = 10;
	printf("External Variable: %d \n", external_variable);
}
// File: file.h
extern int external_variable = 1000;
```

<hr>

> Data Types in C

|Types					|	Data Types|
| :---    |     	---: |
|*Basic Data Type*	|		`int` `char` `float` `double`
|*Derived Data Type*	|	`array` `pointer` `struct` `union`
|*Enumeration Data Type*|	`enum`
|*Void Data Type*|			`void`

> Basic Data Types
The memory size of the basic data types may **CHANGE** according to 32 or 64-bit operating system.

>Example according to 32-bit architecture:

| Data Types				| Memory Size(Byte)	| Range			|	
| :---    |    :----:   | 	---: |
| `char`							|		**1**			|	*-128 to 127*		|
| `signed char` 				|		**1**			|	*-128 to 127*			|
| `unsigned char`			|		**1**			|  *0 to 255*			|
| `short`						|		**2**			|			...		|
| `signed short`			|		**2**				|		...			|
| `signed short int`		|		**2**			|		...			|
| `unsigned short`		|		**2**		|			...		|
| `int`								|		**2**			|		...			|
| `signed int`					|		**2**	|		...			|
| `unsigned int`			|		**2**				|				...	|
| `long int`						|		**4**			|			...		|
| `signed long int`		|		**4**		|		...			|
| `unsigned long int`	|		**4**	|	...				|
| `float`							|		**4**	|		...			|
| `double`						|		**8**			|			...		|
| `long double`				|		**10**			|			...		|
<hr>

***C Operators***

| Categories		| Operators 		|
| :---    		| 			---: |
| Postfix		| 	`()`   `[]`  ` ->`  ` .`  ` ++ ` ` --` |
| Unary			|	`+`   `-`   `!`   `~ `  `++`   `--`   `&`   `data_type*`   `sizeof`  |
| Multiplicative	|	`*`   `/`  ` %` |
| Additive		|	`+`   `-` |
| Shift			|	`<<`   `>>` |
| Relational		|	`<`   `>`   `<=`   `=>` |
| Equality		|	`==`   `!=` |
| Bitwise AND		|	`&` |
| Bitwise OR		|	`ǀ` |
| Bitwise XOR		|	`^` |
| Logical AND		|	`&&` |
| Logical OR		|	`ǀǀ` |
| Conditional		|	`? :` |
| Assignment		|	`=`   `+=`   `-=`  `*=`   `/=`   `%=`   `>>=`   `<<=`   `&=`   `ǀ=`   `^=` |
| Comma			| 	`,` |


For complement operator `~` is the `1's complement`.
<hr>

***Escape Sequence in C***

|	Escape Sequence		|Meaning				
| :---    | 	---: |	
|		`\a`			|		Alarm or Beep	 |			
|		`\b` 				|	Backspace		 |		
|		`\n` 					|New Line			 |	
|		`\t` 		|			Tab Horizontal		 |
|		`\r` 			|		Carriage Return	 |
|		`\'`					|Single Quote	 |			
|		`\"`					|Double Quote	 |	
|		`\ooo`					|Octal Value	 |	
|		`\xhh`			|	Hexadecimal Value |
|		`\0` 				|	Null Value |				
|		`\\` 					| Backslash |				

> Specific Examples:

``` C
#include <stdio.h>
int main(int argc, char** argv) {
	printf("The statement after \0 is omitted");	// The statement after 
	char a = '\124';				//（octal）-> 84 in decimal, ASCII(84) = T
	char b = '\x5b';				//（hexadecimal）-> 91 in  decimal, ASCII(91) = [
	printf("%c", a);				// T
	printf("%c", b);				// [
	return 0;
}
```

<hr>

***Constants in C***

> Two ways to define constant in C:

>-	1. 'const' keyword

``` C
const float PI = 3.14;
printf("The value of PI is: %f", PI);
```

>-	2. '#define' preprocessor

``` C
#define PI 3.14
void main(void) {
	printf("%f", PI);
}
```

<hr>

***C Boolean***

``` C
// in stdbool.h, false = 0, true = 1
#include <stdio.h>
#include <stdbool.h>
int main() {
	bool x = false;
	if(x == true) {
		printf("x is true.\n");
	} else {
		printf("x is false.\n");
	}
	return 0;
}
```
<hr>

***Static in C***

>`static` keyword can be used in following situations in C:
>-	 Static global variable
>-	 Static local variable
>-	 Static function
``` C
	// The static function can be accessed within a file only. 
	static void func() { printf("Hello C\n"); }
```
<hr>

***Programming Errors in C***

> Syntax error
``` C
Int a;
```
> Run-time error
		
``` C
int a = 2 / 0;
```

> Linker error
		
``` C
int Main() {
	int a = 10;
	return 0;
}
```
		
	
> Logical error
``` C
int sum =100;
int k = 1;
for(int i=0; i<=10; i++);	// the inner statement of the for loop will only execute once as a code block, not part of the for loop.

{
	sum = sum + k;
	k++;
}
	
printf("%d", sum);		// 101
```

> Semantic error
``` C
int i; 
i = i + 2;
int j = "it is an integer not a string!!";
int a,b,c;
a + b = c;
int a[10];
a[10] = 34;
```
<hr>

***Conditional Operator in C***

>Syntax:
	
	Expression ? expression1 : expression2;

>Example:
``` C
#include <stdio.h>
int main() {
	int age;
	printf("Please enter your age: ");
	scanf("%d", &age);
	(age >= 18) ? (printf("eligible for voting.\n")) : (printf("not eligible for voting yet.\n"));
	return 0;
}
```

<hr>

***Format Specifiers in C***

| Format Specifiers	|		Type of Output		|
| :---    | 	---: |							
|	`%d` or `%i` 	|		*Signed Decimal Integer or Signed Integer*		|		
|	`%u`		|			*Short Unsigned Integer*			|			
|	`%ld` 		|			*Long Decimal Integer*			|		
|	`%f` 		|			*Signed Float*			|		
|	`%lf` 		|			*Double*				|			
|	`%e` or `%E` 		|		*Mantissa Exponent*					|		
|	`%g`		|			*Exact Precision*					|		
|	`%lf`		|			*Long Double*					|		
|	`%p` 		|			*Printing Memory Address in Hexadecimal Form*	|		
|	`%c`		|			*Signed Character*				|		
|	`%s` 		|			*String or Sequence of Character(s)*		|		
|	`%o` 		|			*Octal Integer*					|		
|	`%x` or `%X`		|		*Hexadecimal Integer*					|		

**Attention**: `%c`, `%d` are usually frequently inter-used because of ASCII.

Specific Examples:
```C
#include <stdio.h>
int main() {
	float a = 12.5;
	float b = 3;
	float c = 3.8;
	printf("The floating-point of a is: %e\n", a);		// The floating-point of a is: 1.250000e+01
	printf("The floating point of b is: %f\n", b);		// The floating point of b is: 3.000000
	printf("The floating point of c is: %g", c);		// The floating point of c is: 3.8  
	return 0;
}
```

<hr>

***C IF ELSE STATEMENT***

> Syntax:

```C
if(condition1) {
	// ...
} else if(condition2) {
	// ...
} else if(condition3) {
	// ...
} else {
	// ...
}
```
	
<hr>

***C SWITCH STATEMENT***

> Syntax:
```C
switch(expression) {
	case value1:
		// ...
		break;
	case value2:
		// ...
		break;
	case value3:
		// ...
		break; 
	case valueN:
		// ...
		break;
	default:
		// ...
}
```
	
<hr>

***C LOOPS***

 - `do ... while`
 
```C
do {
	...
} while(condition);
```
 - `while`
```C
while(condition) {
	...
}
```
 - `for`
```C
for(; ;) {
	...
}
```
<hr>

***`goto` Statement in C***

 - Jump to a label

```C
#include <stdio.h>
int ret() {
	static int count = 0;
	count++;
	return count;
}
int main() {
jump_back:
	printf("jump back\n");
	if(ret() < 10) {
		goto jump_back;
	} else {
		goto jump_forward;
	}
	printf("This code will not be executed.\n");
jump_forward:
	printf("jump forward\n");
	return 0;
}
```

 - Storing the address of a label
```C
void *ptr = &&jump;
jump:
	printf("hi\n");
	goto *ptr;
```
 - Jump / Branch Table in C
```C
#include <stdio.h>
#include <stdlib.h>
typedef void (*Handler) (void);
void func0(void) { printf("0\n"); }
void func1(void) { printf("1\n"); }
void func2(void) { printf("2\n"); }
void func3(void) { printf("3\n"); }
Handler jump_table[4] = {func0, func1, func2, func3};
int main(int argc, char **argv) {
	int value = atoi(argv[1]) % 4;
	jump_table[value]();
	return 0;
}
```

<hr>

***C BREAK & CONTINUE STATEMENT***

>For `break`: 
>>it only breaks the inner loop in nested loop situation.

>For `continue`: 
>>it skips the lines of code after it.

<hr>

***Type Casting in C***

> Syntax: 
		(data_type) value;

> Examples:
 
```C
int without_type_casting = 9 / 4;
float with_type_casting = (float) 9/4;
printf("9/4 without type casting: %d\n", without_type_casting);		// 9/4 without type casting: 2
printf("9/4 with type casting: %f\n", with_type_casting);		// 9/4 without type casting: 2.250000
```

	
<hr>

***Functions in C***

> Syntax:

```C
return_type function_name(data_type parameter ...) {
	// TODO
}
```
	
> Examples:

```C
#include <stdio.h>
void print1(int);					// declare first later define.
void print2(int x) { printf("print2: %d\n", x); }	// declare and define.
int main() {
	int x = 100;
	print1(x);
	print2(x);
	return 0;
}
void print1(int x) { printf("print1: %d\n", x); }
```

<hr>

***Types of functions:***

> 1. library functions:
		are the functions which are declared in the C header files such as scanf(), printf() etc.
		Position in Linux:	/use/lib/...
			
> 2. user-defined functions:
		are the functions which are created by the C programmer.

<hr>

***Frequently used C header files:***
|Header File| Description |
|:--|:--|
|	`stdio.h`	| *standard input/output header file.* |
|`conio.h`		| *console input/output header file.*|
| `string.h`		| *contains all string related library functions like gets(), puts(), etc.*|
|	`stdlib.h`		| *contains all the general library functions like malloc(), calloc(), exit(), etc.*|
| `math.h` 		| *math header file.*|
| `time.h` 		| *contains all the time-related functions.*|
|`ctype.h` 		| *contains all character handling functions.*|
| `stdarg.h` 		| *variable argument functions are defined in this header file.*|
| `signal.h` 		| *all the signal handling functions.*|
| `setjmp.h` 	| *all the jump functions.* |
|`locale.h` 		| *locale functions.* |
|`errno.h` 		| *error handling functions.* |
|`assert.h` | *diagnostics functions.* |


<hr>


