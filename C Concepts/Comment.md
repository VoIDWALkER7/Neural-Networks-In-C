Comments are lines or texts that are ignored by the compiler while compiling the program.
In C, a comment is denoted by // 
eg:
```C
//this is a comment 
```
If you want to have multiple lines as comments, it starts with ```/*``` and ends with ```*/``` 
eg:
```C
/* 
This is comment line 1
this is comment line2
this is comment line 3
*/

```
We use comments to describe the code block, so that when we are going through a large code, or a complicated code, comments can be used to give explanations within the code without referencing the documentation unless necessary.  
eg of application of comments in code: 
```C
#include <stdio.h>

int main(){
	//i = rows, j = cols
	for(int i = 0; i< 10; i++){
		for(int j =0; j<10; j++){
			printf("+ ");
		}
		printf("\n");
	}
	//the code above prints a square made of + signs. 
}
```

[[Loops]](https://github.com/VoIDWALkER7/Neural-Networks-In-C/blob/main/C%20Concepts/Loops.md)←PREVIOUS

NEXT → [[Arrays]] 
