### While loop
```C
#include <stdio.h>
int main(){
	while([condition]){
		printf("*");
	}
}
```
- condition → the condition is the condition under which the while loop will function. 
- For eg: 
```C
int num_stars = 10;
	while (num_stars > 0){
		printf("*");
		num_stars = num_stars - 1;
	}
```
while loops are great for dealing with complex data structures like pointers
### Do-while loop
```C
#include <stdio.h>
int main(){
	do{
	printf("*");
	}
	while([condition]);
}
```
- Difference between the while loop and the do while loop is that in do - while loop the loop body runs first and then the condition is checked, while in while loop the condition is checked first and then the loop body is run. 
eg:
```C
int num_stars = 10;
	do{
		printf("*");
		num_stars = num_stars - 1;
	}while(num_stars > 0);
```

> [!NOTE] Findings 
> for some reason, in C or rather gcc characters inside ‘ ’ are not considers strings, but “ ” are considered strings.
### For Loop
```C
#include <stdio.h>
int main{
	for([initializer]; [condition]; [update] ){
	
	}
}
```
- initializer → the variable that starts the count in the loop
- condition → the condition under which the loop functions
- update → the way that variable updates after each loop
```C
for(int num_stars=10;num_stars>0;num_stars = num_stars - 1){
	printf("*");
}
```
- For loops are great for number crunching
 - The initializer exists till the for loop is ongoing, but is discarded as soon as the loop is over. it solely exists for the purpose of the loop unless it is declared outside the loop. 
- Eg of flexibility of for loop:
```C
int num_stars = 10;
for (;num_stars>0;num_stars = num_stars -1){
	printf"*");
}
printf(num_stars);//0
```

```C
int num_stars = 10;
for (; num_stars > 0;) {
	printf("+");
	num_stars = num_stars - 1;
}
```
- Normally for discardable  initializers, we use single letter variables, like i. 
- When we write the update we have been writing like this : i = i - 1, but we can also write it like this : 
```C
for (int i = 10; i > 0 ; i -= 1){
	printf("+");
}
```
![[update form output check.png]]
works just the same. 
any operator can work just the same. 
We also have other ways to write the operators.
Also, if we just have to do operation using one, we can:
```md
++i → first add 1, then call the variable → eg: i = 0, ++i → 1
i++ → first call the variable, then add 1 → eg: i = 0, i++ → 0
--i -> first subtract 1, then call the variable -> eg: i = 1, --i -> 0
i-- -> first call the variable, then subtract 1 -> eg: i = 1, i-- -> 1
```
#### Nested For Loops

```C
for (int i = 10; i > 0; i-- ){
	for(int j = 10; j>0; j--){
		printf("+");
	}
	printf("\n");
}
```
![[Nested For Loop output.png]]
- The one with the variable i is the outer loop, while the one with the variable j is the inner loop. 
- The outerloop first goes on to the inner loop and then the inner loop is executed first and after that after exiting the loop, the line after the loop is exited and so on until the outer loop is exited or restarted. The cycle continues. 
```C
#include <stdio.h>

int main(){
       
        for (int i = 10; i > 0; i-- ){
                for (int k=0; k<i; k++){
                        printf(" ");
                }
                for (int j = 10; j > i; j--){
                        printf("+");
                }
                printf("\n");
        }              
}

```
this is the code for this:
![image](https://github.com/VoIDWALkER7/Neural-Networks-In-C/blob/main/C%20Concepts/The%20pattern.png)

we can also form shapes like this by just adding a space after + in “+”: 
![image](https://github.com/VoIDWALkER7/Neural-Networks-In-C/blob/main/C%20Concepts/Pyramid.png)

[[Operators]](https://github.com/VoIDWALkER7/Neural-Networks-In-C/blob/main/C%20Concepts/Operators.md)← Previous

NEXT → [[Comment]] 
