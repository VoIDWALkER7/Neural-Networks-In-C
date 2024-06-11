# Syntax & Formatting
- End of line is denoted by “;”
## Function Syntax:
- First Comes the Type of the Function, such as: int
- Then comes the name of the functions
-  After that it’s followed by parentheses, which can also include parameters
-  Then Curly braces are added, and inside those curly braces we define what the function will be doing, and what other functions will be called and how it will deal with it’s parameters. 
	```C
int hello(){
	printf("hello"); 
}
	```
	

- Special Elements for Formatting - Escape Sequence:
	- `\n` : To Enter the next line and type whatever is written after it. 
	- `\t` : To Add multiple spaces between two characters. 
- Formatting Variables, Strings, Integers into strings:
	- `%d` : Used to transfer integer into string. (If you use %2d, it will take minimum spacing for padding, making the values look symmetric)
	```C
	printf("My age is: %d ", 42);
	//or
	int age = 42;
	printf("My age is: %d", age);
	printf("My age is: %2d", age)
```
- Declaring a Variable:
	- First set the data type, eg: int, char, float, and so on. 
		- You can also add a prefix called signed before int to make it a signed integer, eg: 
```C
signed int trik = -3;
```
	- Then, specify the name of the variable:
		- Variable can’t have any symbol other than an underscore. It can also start with underscore. 
		- Variables can’t begin with numbers. nor can it only consist of numbers. 
		- Variable names can’t coincide with keywords. Eg: you can’t name a variable printf. 
	- After that, you add the = so that the variable can store the value that will come after =. 
	- For strings, there should be double quotes, “” around it. For integer, no double quotes are required. 
	- At the end, there should be a semicolon. 
- **sizeof** command: 
	- syntax: - 
		```C
sizeof(/*whatever you want the size of*/);
//eg
sizeof(int)
```
	- Usage: 
		- To find the size of any variable, data type, array, string, and so on. 
		- It’s the size that it occupies on the memory. 
		- For int, it’s 4 bytes. 
```C
#include <stdio.h>  
  
int main(){  
       printf("\n        Char : %2d", sizeof(char));  
       printf("\n       Short : %2d", sizeof(short));  
       printf("\n         Int : %2d", sizeof(int));  
       printf("\n       Float : %2d", sizeof(float));  
       printf("\n        Long : %2d", sizeof(float));  
       printf("\n      Double : %2d", sizeof(double));  
       printf("\n   Long Double : %2d", sizeof(long double));  
  
       return 0;  
}
```

[[Hello World]] ← PREVIOUS
NEXT → [[Primitive Data Types & Binary Basics]]