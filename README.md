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


***stdio.h***

>Standard Input/Output Header:
		It defines several types, macros, and functions that allow you to perform file I/O, console I/O, and other types of I/O in your C programs.	

 - Console input/output functions:
```C
int printf(const char *format, ...);
int scanf(const char *format, ...);

// it reads the next character from the input stream and returns its ASCII code as an integer value, returns EOF (-1) if the end of the input stream is reached.
int getchar(void);	

// prints a string to the console or other output stream, automatically appends a newline character('\n') to the end of the string before printing it.
int puts(const char *str);	

// the 'str' argument specifies the buffer where the input text should be stored, it reads characters from the input stream until it encounters a newline character (\n) or the end-of-file indicator. 
// The newline character is replaced by a null character (\0) and the resulting string is stored in the buffer specified by str. 
// However, it is considered unsafe because it does not perform any bounds checking on the buffer size. So the use of `fgets()`is more favoured.
char *gets(char *str);

int getc(FILE *stream);
int putc(int c, FILE *stream);
	
```
	
 - File input/output functions:
 ```C
// returns a pointer to a FILE structure that represents the opened file or NULL.
FILE *fopen(const char *filename, const char *mode);	

// The 'filename' argument specifies the name of the file to be associated with the stream.
FILE *freopen(const char *filename, const char *mode, FILE *stream);

// returns zero on success and a non-zero value if an error occurs.
int fclose(FILE *stream);	

fread()
fwrite()
fprintf()
fscanf()
fgets()
fputs()
fseek()
ftell()
rewind()
feof()	
remove()
rename()
fileno()
fdopen()
fgetpos()
fsetpos()
getline()
getdelim()
fgetc()
fputc()
popen()
pclose()
```
	
 - File pointer macros:
 ```C
extern FILE *stdin
extern FILE *stdout	
extern FILE *stderr	
#define EOF (-1)
#define SEEK_SET 0
#define SEEK_CUR 1
#define SEEK_END 2
#define BUFSIZ 1024
#define FILENAME_MAX 260
#define TMP_MAX 32767
#define L_tmpnam 25
#define FOPEN_MAX 20
#define NULL ((void*)0)
#define P_tmpdir "/tmp/"
```

- Other functions & macros:
```C
feof()
ferror()
fflush()
perror()
setbuf()
setvbuf()
tmpfile()
tmpnam()
```
	
<hr>

***Change the Output Stream of puts() Function***

```C
#include <stdio.h>
int main() {
	FILE *file = fopen("output.txt", "w");
	if (file == NULL) {
		perror("Error opening file");
		return 1;
	}
	// Redirect standard output to the file.
	if (freopen("output.txt", "w", stdout) == NULL) {
		perror("Error redirecting stdout");
		return 1;
	}
	// Write a string to the file using puts()
	puts("Hello, world!");
	// Close the file and restore standard output.
	fclose(file);
	freopen("CON", "w", stdout);
	return 0;
}
```

<hr>

***conio.h***

<hr>

***Difference between getchar() and getch()***


>	`getch()` is a non-standard function that reads a single character from the console without echoing it to the screen, and read it immediately even before typing the next character, 
>
>	while `getchar()` is a standard function that reads a single character from the console and echoes it to the screen.

```C
#include <stdio.h>
#include <conio.h>
int main() {
	char ch1, ch2;
	printf("Enter a character: ");
	ch1 = getchar();
	printf("You entered: %c\n", ch1);
	printf("Enter another character: ");
	ch2 = getch();
	printf("You entered: %c\n", ch2);
	return 0;
}
/* Output
	Enter a character: a
	You entered: a
	Enter another character: You entered: a
*/
```

<hr>

***string.h***

<hr>

***stdlib.h***

<hr>

***math.h***

<hr>

***time.h***

<hr>

***ctype.h***

<hr>

***stdarg.h***

<hr>

***signal.h***

<hr>

***setjmp.h***

<hr>

***locale.h***

<hr>

***errno.h***

<hr>

***assert.h***

<hr>

***unistd.h***

<hr>

***Call by Reference in C***
```C
void swap(int *x, int *y) {
	int temp = *x;
	*x = *y;
	*y = temp;
}
```

<hr>

***Swap two integers using bit manipulaltion without temporary value***

```C
a ^= b;
b ^= a;
a ^= b;
```

<hr>

***Storage Classes in C***
| Storage Classes	 | Storage Place | Default Value |	Scope	Life Time|
|:-- | -- | -- | :-- |
| `auto`	|			**RAM**			|	garbage value | *localwithin the function*|
|`extern`	|		**RAM**			|	zero	|			*global	till the end of the main program*|
| `static`  | **RAM** |	zero | 				*local		till the end of the main program* |
| `register`|		**Register**		|	garbage value|		*local		within the function*|

<hr>

***C Array***

> Advantage of C Array
> - *Code Optimization*
> - *Ease of Traversing*
> - *Ease of Sorting*
> - *Random Access*

> Disadvantage of C Array
> - *Fixed Size*

>Declaration of C Array:
		`data_type array_name[array_size];`

> Examples of declaring an array in  C:
```C
int marks1[5];
marks1[0] = 10;
marks1[1] = 20;
marks1[2] = 30;
marks1[3] = 40;
marks1[4] = 50;
int marks2[5] = {10, 20, 30, 40, 50};
int marks3[] = {10, 20, 30, 40, 50};
int marks4[5];
for(i = 0; i<5; i++) { scanf("%d",&marks4[i]); }  
```
<hr>

***Two Dimensional Array in C***

```C
data_type array_name[rows][columns];
/* matrix of 4 rows and 3 columns. */
int twodim[4][3] = {
	{1, 2, 3},
	{2, 3, 4}, 
	{3, 4, 5}, 
	{4, 5, 6}
};
```

<hr>

***Passing an array in function***
```C
#include <stdio.h>
int *bubble_sort(int[]);
int main() {
	int a[10] = {4, 9, 7, 2, 1, 3, 5, 0, 6, 8};
	int *new_a = bubble_sort(a);
	return 0;
}
int *bubble_sort(int a[]) {
	int temp;
	for(int i=0; i<10; i++) {
		for(int j=i+1; j<10; j++) {
			if(a[j] < a[i]) {
				temp = a[i];
				a[i] = a[j];
				a[j] = temp;
			}
		}
	}
	return a;
}
```

<hr>

***C Pointers***
> The pointer in C language is a variable which stores the `address` of another variable.

>The size of the pointer depends on the architecture. However, in *32-bit* architecture the size of a pointer is *2 byte (32 bits)*.

> Declaring a pointer:
```C
int *a;		// a pointer to `int`
char *c;	// a pointer to `char`
```

> Pointer Example:
```C
int number = 50;
int *p_number = &number;
printf("address of number: %x", p_number);
printf("value of number: %d", *p_number);
```

> Pointer to an array
```C
int arr[10];	// an array of 10 integers.
int *p[10];	// an array 10 pointers of which each 
```

> points to integers.
```C
for(int i=0; i < 10; i++) {
	p[i] = arr + i;
	p[i] = &arr[i];		// both okay ^^.
}
int matrix1[][3] = {
	{1, 2, 3},
	{4, 5, 6},
	{7, 8, 9}
};
int matrix2[][3] = {
	1, 2, 3,
	4, 5, 6,
	7, 8, 9
}
int *p_matrix = matrix1;
for(int i = 0; i < 9; i++) { printf("%d ", *(p_matrix+i)); }
```

> Pointer to a function
```C
void display(int);
void (*p)(int) = &display;
void (*p)(int) = display;	// both okay :-)
```

> To call the function pointer
```C
p(100);
(*p)(100);			// both okay x-)
```

> Pointer to structure
```C
struct st { 
	int i;
	float f;
} ref;
struct st *p = &ref;
```

> `NULL` Pointer
```C
int *p = NULL;
```
	

> Adress Of (&) Operator
```C
int number = 50;
printf("The value of number is: %d, the address of number is %u", number, &number);
```

<hr>

***C Double Pointer (Pointer to Pointer)***
```C
#include <stdio.h>
int main() {
	int a = 10;
	int *ptr_a = &a;
	int **pptr_a = &p;
	printf("address of a: %x\n", ptr_a);
	printf("address of ptr_a: %x\n", pptr_a);
	printf("value stored at ptr_a: %d\n", *ptr_a);
	printf("value stored at pptr_a: %d\n", **pptr_a);
	// arr[0] == *(arr) == *(arr+0) == *p[0] == **(p+0) == **(pp+0) == 10
	int arr[] = {10, 20, 30, 40, 50};			// int arr[] == int *arr
	int *p[] = {arr, arr+1, arr+2, arr+3, arr+4};		// int *p[] == int **p
	int **pp = p;
	printf("%d %d %d\n", pp-p, *pp-arr, **pp); // 0 0 10
	pp++;	// pp++ == pp + sizeof(int)
	printf("%d %d %d\n", pp-p, *pp-arr, **pp); // 1 1 20
	*pp++;	// *pp++ == *(pp++)
	printf("%d %d %d\n", pp-p, *pp-arr, **pp); // 2 2 30
	++*pp;	// ++*pp == ++(*(pp))
	printf("%d %d %d\n", pp-p, *pp-arr, **pp); // 2 3 40
	++**pp;	// ++**pp == ++(**(pp))
	printf("%d %d %d\n", pp-p, *pp-arr, **pp); // 2 3 41
	return 0;
}
```

>	`Pointer` has a great importance in C programming, so hereby let us fully comprehend the code above. (from arr to return 0)
>	Firstly, arr represents an integer array of size 5, and p represents the array that contains pointers.
>	Secondly, pp is basically the same as p, just another written form, the share the same value but NOT same reference.
>	Thirdly, *p == arr, which if by using computer memory representation is that 
```C
arr, arr+1, arr+2, arr+3, arr+4 	-> 61ff08, 61ff0c, 61ff10, 61ff14, 61ff18
p, p+1, p+2, p+3, p+4			-> 61fef4, 61fef8, 61fefc, 61ff00, 61ff04
*p, *(p+1), *(p+2), *(p+3), *(p+4) 	-> 61ff08, 61ff0c, 61ff10, 61ff14, 61ff18
pp, pp+1, pp+2, pp+3, pp+4 		-> 61fef4, 61fef8, 61fefc, 61ff00, 61ff04

```
>	So, arr contains the address of the numbers, and p / pp contains the address of each arr.
>	Fourthly, when doing arthmetic operations of pointers, it is not simply inrement or decrease by 1,
>	but by the value divides the size of the data type, for example

```C
int numbers[] = {...};
int *p = numbers;
```
		
>	then, by doing p++ or p+1 it automatically means address of p + size of int which is by this machine '4' rather than '1'.


<hr>

***Pointer Arithmetic in C***

	1. Increment
		If we increment a pointer by 1, the pointer will start pointing to the immediate next location.
		And when we increment more than 1, let us say increase i times, it is given below:
		new_address = current_address + i * size_of(data_type)
	2. Decrement
		Same logic as with increment:
		new_address = current_address - i * size_of(data_type)
	3. Addition
		Assume that a value n was added to the pointer variable, then:
		new_address = current_address + (n * size_of(data_type))
	4. Subtraction
		When pointer subtracts pointer, it displays the value of the distance between two pointers:
		Address1 - Address2 = (Subtraction of two addresses) / size_of(data_type)
	5. Comparison
		<, <=, >, >=, ==, !=
		But only with pointers which point to the same data type!!!

***Illegal arithmetic with pointers***

	address + address
	address * address
	address / address
	address & ^ | address
	~address
	
<hr>

***Dangling Pointers in C***

> The most common bugs related to pointers and memory management is dangling/wild pointers.
Dangling pointer happens when the programmer fails to initialize the pointer with a valid address.
So make sure to set the pointer of `NULL` value when the memory was free-ed.

1. Deallocation of memory
```C		
int *ptr = (int *)malloc(sizeof(int));
*ptr = 10;
free(ptr);
// here ptr acts as a dangling pointer, prints garbage value in the output console.
printf("%d", *ptr);	
```
2. Function call
```C
int *dangling_pointer() {
	// temp variable has local scope.
	int temp = 10;
	// returning address of temp variable.
	return &temp;
}
int main() {
	// ptr will point to some garbage value, as temp variable will be destroyed after the execution of below line.
	int *ptr = dangling_pointer();
	// ptr is a dangling pointer now, which contains some random address and is pointing to some garbage value.
	printf("%d", *ptr);
	return 0;
}
```
3. Variable goes out of scope
```C
int *ptr;
{
	int temp = 10;
	ptr = &temp;
}
// prints out garbage value.
printf("%d", *ptr);
```
<hr>

***Constant in C Pointers***

> A `constant pointer` in C cannot change the address of the variable to which it is pointing,
i.e., the constant pointer ***cannot point to any other variable***, once it is set.

Syntax:
```C
<type of pointer> * const <name of pointer>;
```
	
Example:
```C
int a = 1;
int * const ptr;
ptr = &a;
```
	
> A `pointer to constant` in C is a pointer which the value of the variable that the pointer points connot be changed.
i.e., the address of these pointers can be changed, but ***cannot change the value of the variable*** that the point points.

*Syntax:*
```C
const <type of pointer> * <name of pointer>
```
	
*Example:*
```C
int a = 100;
int b = 200;
const int * ptr;
ptr = &a;
ptr = &b;
```
	
> A `constant pointer to a constant` is a combination of the above two pointers.

*Syntax:*
```C
const <type of pointer> * const <name of pointer>
```
	
*Example:*
```C
int a = 10;
const int * const ptr;
ptr = &a;
```
	
<hr>

***Void Pointer in C***

> Void pointer means a generic pointer that can point to any data type.
*Syntax:*
```C
void *<pointer name>
```

*Example:*
```C
int a = 90;
float b = 4.5;
char c = 'k';
void *ptr = NULL;
ptr = &a;
printf("Value of the void pointer: %d \n", *((int*)ptr));
ptr = &b;
printf("Value of the void pointer: %f \n", *((float*)ptr));
ptr = &c;
printf("Value of the void pointer: %c \n", *((char*)ptr));
```

<hr>

***Funtion Pointer in C***

*Introduction:*
```C
#include <stdio.h>
void test() { return; }	// test function does nothing.
int main() {
	int a = 5;
	printf("Address of the variable a: %p\n", &a);
	printf("Address of the function test: %p\n", test);
	return 0;
}
```

*Syntax of function pointer in C:*
```C
return_type (*pointer_name) (data_type_arg_1, data_type_arg_2, ...);
```

*Example:*
```C
float foo(int, int);
float (*foo_pointer) (int, int);
foo_pointer = foo;
```

*Calling a function through a function pointer in C:*
```C
// When using a function pointer, we can simply call its name or deferece it.
#include <stdio.h>
int square(int);
int (*area) (int) = square;
int main() {
	int n = 10;
	printf("area of n: %d\n", square(n));		// 100
	printf("area of n: %d\n", area(n));			// 100
	printf("area of n: %d\n", (*area)(n));		// 100
	return 0;
}
int square(int n) { 
	return n*n; 
}
```

*Array of function pointers*
```C
#include <stdio.h>

float add(int, int);
float subtract(int, int);
float multiply(int, int);
float divide(int, int);

int main() {
	int a, b;
	float results[4];
	float (*operation[4]) (int, int);
	
	operation[0] = add;
	operation[1] = subtract;
	operation[2] = multiply;
	operation[3] = divide;
	
	printf("Enter two values: ");
	scanf("%d %d", &a, &b);
	
	for(int i = 0; i < 4; i++) {
		// results[i] = operation[i](a, b);
		// results[i] = (operation[i])(a, b);
		results[i] = (*operation[i])(a, b);
	}
	
	printf("Addition (a+b) = %.1f\n", results[0]);
	printf("Subtraction (a-b) = %.1f\n", results[1]);
	printf("Multiplication (a·b) = %.1f\n", results[2]);
	printf("Division (a/b) = %.1f\n", results[3]);
	
	return 0;
}
float add(int a, int b) { return a+b; }
float subtract(int a, int b) { return a-b; } 
float multiply(int a, int b) { return a*b; }
float divide(int a, int b) { return a/(b*1.0); }
```

*Funtion pointer passed as an argument*
```C
#include <stdio.h>

int conditional_sum(int a, int b, int (*ptr)(int)) {
	a = ptr(a);
	b = ptr(b);
	return a + b;
}
int square(int a) {
	return a * a;
}
int cube(int a) {
	return a * a * a;
}

int main() {
	int (*fp)(int);

	fp = square;
	int sum = conditional_sum(2, 3, fp);
	printf("Square sum: %d\n", sum);

	fp = cube;
	sum = conditional_sum(2, 3, fp);
	printf("Cubic sum: %d\n", sum);
	return 0;
}
```

<hr>

***sizeof() operator in C***

*Syntax:*
```C
sizeof(expression)
sizeof(data_type)
```
*It determines the size of the expression / data type.*

Examples:
```C
int x = 10;
printf("size of the variable x is: %d\n", sizeof(x));		// expression
printf("size of the integer data type is: %d\n", sizeof(int));	// data type
```

<hr>

***C Naming Convention***
	
| name | convention |
|--|--|
|	`Struct` | 						*TitleCase, STitleCase*|
|	`Struct Members`	|			*lower_case*|
|	`Enum`					|	*TitleCase, ETitleCase*|
|	`Enum Members`	|			*ALL_CAPS*|
|	`Functions`					|	*this_is_a_function()*|
|	`Functions indirectly called` |		*_this_is_a_function()*|
	
<hr>

***Dynamic memory allocation in C***

*Dynamic memory allocation in C language is possible by four functions of <stdlib.h> header file*

	1. malloc()	allocates single block of requested memory.
	2. calloc()	allocates multiple block of requested memory.
	3. realloc()	reallocates the memory occupied by malloc & calloc
	4. free()	frees the dynamically allocated memory.


*Difference between "static"(s) & "dynamic"(d) memory allocation:*
|static| dynamic |
|--|--|
|	memory is allocated at `compile` time.	|memory allocated at `run` time.|
|	memory `cannot` be increase during execution.	|	memory `can` be increased during execution.
|	used in `array`.		|			used in `linked list`.|	


*malloc() function in C*
>	Works `faster` than *calloc*.
	1. It `doesnot` initialize memory at execution time, so it has garbage value initially.
	1. It returns `NULL` if memory is not sufficient.

*Syntax:*
```C
data_type *ptr = (type_cast*)malloc(byte_size_in_total);
```
*Example:*
```C
int *ptr = (int*)malloc(10*sizeof(int));
if(ptr == NULL)                         
{    
	printf("Sorry! unable to allocate memory\n");    
	exit(0);    
}
```

*calloc() function in C*
> Later introduced after *malloc*.
	1. It `does` initialize all bytes to zero.
	2. t returns `NULL` if memory is not sufficient.

*Syntax:*
```C
data_type *ptr = (type_cast*)calloc(number, single_byte_size);
```

*Example:*
```C
int *ptr = (int*)calloc(10, sizeof(int));
if(ptr == NULL)                         
{    
	printf("Sorry! unable to allocate memory");    
	exit(0);    
}    
```

*realloc() function in C*
*Syntax:*
```C
ptr = (type_cast*)realloc(ptr, new_size);
```
*Example:*
```C
char *str = (char*)malloc(15 * sizeof(char));
str = (char*)realloc(str, 25);
if(str == NULL)                         
{    
	printf("Sorry! unable to reallocate memory");    
	(0);    
}
```

*free() function in C*
*Syntax:*
```C
void free(void  *ptr);
```
*Example:*
```C
char *str = (char*)malloc(15 * sizeof(char));
free(str);
str = NULL;
```

<hr>

***Command Line Arguments in C***

*To support the command line argument, we need to change the structure of main() function as given below:*
```C
int main(int argc, char *argv[]) { return 0;} 
int main(int argc, char **argv) { return 0; }
```
*Example:*
```C
// file: test.c
#include <stdio.h>
int main(int argc, char **argv) {
	if(argc == 1) {
		printf("No argument passed through command line.\n");
	} else {
		printf("First argument is %s\n", argv[1]);
	}
	return 0;
}
// ./test hello		-> 	output: First argument is hello
```

<hr>

***C Structure***

*Syntax:*
```C
struct StructureName {
	data_type member1;
	data_type member2;
	...
	data_type memberN;
};
```

*Example:*
```C
struct Employee {
	int id;
	char name[20];
	float salary;
};
```

*Declaring Structure Variable:*
```C
struct Employee1 {
	int id;
	char name[20];
	float salary;
};

struct Employee2 {
	int id;
	char name[20];
	float salary;
} e2, e3;

int main() {
	struct Employee1 e0, e1;
	return 0;
}
```

>*Accessing members of the structure
	1. by `.`		(dot operator)
	2. by `->`	(structure pointer operator)*
	
>*Initialization & assignment in structure*
```C
struct point {
	int x; 
	int y;
};
struct point p0 = {1, 2};
struct point p1 = {.y = 2, .x = 1};
struct point p = p0;
```

*Pointers to structure*
```C
struct point *p = &p0;
(*p).x = 10;	// set the 'x' element of the structure to 10
p->x = 100;	// set the 'x' element of the structure to 100
```

*Structure as Return Type*
```C
typedef struct {
    int x;
    int y;
} Point;

Point add_points(Point a, Point b) {
    return (Point) {a.x + b.x, a.y + b.y};
}

Point p1 = {3, 4};
Point p2 = {1, 2};
Point p3 = add_points(p1, p2); 	// p3.x = 4,  p3.y = 6
```



*Bit Field*
```C
struct BoxProperties {
	unsigned int transparent	: 1;
	unsigned int fillcolor 		: 3;
	unsigned int			: 4;		// fill up 8 bits.
	unsigned char width		: 4;
	unsigned char height		: 4;	
};

struct A{
	int i;
	int j;
} a;

struct B{
	int i	: 1;
	int j	: 1;
} b;

printf("%d %d\n", sizeof(a), sizeof(b));	// 8 4
```


<hr>

***typedef in C***

*The `typedef` keyword is used to redefine the name of an already existing variable.*
*Syntax:*
```C
typedef <existing_name> <alias_name>;
```
*Example:*
```C
typedef unsigned int uint;
uint a, b;				// same as `unsigned int a, b;`
```


*Using typedef with structures*
*approach1:*
```C
struct student {
	int age;
	char name[20];
};
typedef struct student Student;
struct student s0;
Student s1;
```
*approach2:*
```C
typedef struct student {
	int age;
	char name[20];
} Student, *pStudent;
Student s0, s1;
```
*approach3:*
```C
typedef struct Node Node;
struct Node {
    int data;
    Node *nextptr;
};
```

*Using typedef with pointers*
```C
int *a, b;		// equal to `int *a;` and `int b;`
typedef int* int_ptr;
int_ptr p1, p2;		// equal to `int *p1;` and `int *p2;`
```


*'Flexible' Array Member*
```C
struct FlexibleStruct {
	int len;
	int arr[];	// the flexible array member must be the last element.
};

struct FlexibleStruct *generate(int length) {
	struct FlexibleStruct *p_FelxibleStruct = (struct FlexibleStruct*)malloc(sizeof(struct FlexibleStruct) + length*sizeof(int));
	p_FelxibleStruct->len = length;
	for(int i=0; i<length; i++) {
		scanf("%d", p_FlexibleStruct->arr + i);
	}
	return p_FelxibleStruct;
}
```


<hr>

***Advanced `typedef`***

*typedef vs #define*

>	1. `#define` is capable of defining aliaases for values as well, for instance, 
	we can define 1 as ONE, 3.14 as PI. 
		`typedef` is limited to giving symbolic names to data types only.
	2. preprocessors interpret `#define` statements, while the compiler interprets `typedef` statements.
	3. There should be no semicolon `;` at the end of #define, but a semicolon `;` at the end of typedef.
	4. In contrast with #define, 
		typedef will actually `define` a new data type by copying and pasting the definition values.


```C
// Using typedef with functions
typedef int (*MathFunc) (float, int);

int do_math(float arg1, int arg2) { return arg2; }

int call_a_func1(int (*call_this) (float, int)) {
	int output = call_this(5.5, 7);
	return output;
}
int call_a_func2(MathFunc call_this) {
	int output = call_this(5.5, 7);
	return output;
}

int result1 = call_a_func1(&do_math);		// or `int result1 = call_a_func1(do_math);`
int result2 = call_a_func2(&do_math);		// or `int result2 = call_a_func2(do_math);`

// Using typedef with arrays
typedef char arr_t[5];
arr_t a = {0, 1, 2, 3, 4};			// same as `char a[5] = {0, 1, 2, 3, 4};`
arr_t *b;					// same as `char *b[5];`
```

<hr>

***Advanced Structure in C***

*Nested Structure*
1. `Separete`
```C
struct Date {
	int dd;
	int mm;
	int yyyy;
};
struct Employee {
	int id;
	char name[20];
	struct Date date;
};
```

2. `Embedded`
```C
struct Employee {
	int id;
	char name[20];
	struct Date {
		int dd;
		int mm;
		int yyyy;
	} date;
};
```



