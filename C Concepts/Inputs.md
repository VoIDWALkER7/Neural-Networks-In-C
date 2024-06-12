To take inputs through the console in C language, we use scanf function. 
Syntax: 
```C 
int triangle;
scanf("%d", &triangle);
```
Here, we use the address of the variable where we want to send the data we take in input. For integer, we have used %d, but for others, we will use other formats, like: 
```
%c for char
%f for float 
```
and so on. 
Example:
```C
#include <stdio.h>

int main(){
	int x;
	int y;

	printf("What is the first number you want to multiply?:");
	scanf(" %d", &x);
	printf("What is the second number you want to multiply?:");
	scanf(" %d", &y);

	printf(" %d", x*y);
	return 0;
}

```
Output: 
![image](https://github.com/VoIDWALkER7/Neural-Networks-In-C-Notes/blob/main/C%20Concepts/7%20X%203.png)

We can also write the code in the following way: 
```C
#include <stdio.h>

int main(){
	int x;
	int y;

	printf("What are the two numbers you want to multiply?");
	scanf(" %d %d", &x, &y);

	printf(" %d", x*y);
	return 0;
}
```
Output: 
![images](https://github.com/VoIDWALkER7/Neural-Networks-In-C-Notes/blob/main/C%20Concepts/7%20X%208.png)

[[Comment]](https://github.com/VoIDWALkER7/Neural-Networks-In-C-Notes/blob/main/C%20Concepts/Comment.md) ← PREVIOUS

NEXT → [[If Else]](https://github.com/VoIDWALkER7/Neural-Networks-In-C-Notes/blob/main/C%20Concepts/If%20Else.md)
