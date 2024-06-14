Memory address is the address of the memory where the variables are located. 
When we use scanf, we use the address so that we can modify the default value(0) that is stored at the address and change it to whatever the input is. 

```C
scanf("%d%, &input)
```

Now, when you write a function like this: 
```C
#include <stdio.h>

void change(int input){
	input += 10;
	return;
}

int main(){
	int input = 10;
	change(input);

	printf("input = %d",input)

	return 0;
}
```

Then the output that comes out isn’t 20, but still 10. That’s because in C programming we can only pass by value not by reference. 

When we write int input in the function parameter and pass the input through the function, it creates a completely new variable and then manipulates the value of that variable instead of the one we passed through. 

To actually change the value of input, instead of passing the variable, we will pass the address of the variable: 

```C
#include <stdio.h>

void change(int *input){
	*input += 10;
	return;
}

int main(){
	int input = 10;
	change(&input);

	printf("input = %d",input)

	return 0;
}
```
This will work because address is a value, and it’s constant through the run-time of the program, so when the function changes the value stored at the address, it’s gonna change the original value stored at it instead of creating a new memory location and adding to that value there. 

We use * operator to say that the variable is a pointer to the address. 

So, * is the reference operator and & is the address operator in the above program.

[[Arrays]] ← PREVIOUS