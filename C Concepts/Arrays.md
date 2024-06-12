We declare an array using the following format: 
```C
int x[] = {1,2,3,4,5};
```

to access the values according to index, we will do it similarly to how we do it in lists:
```C
printf("\n %d",x[1]);
```
------------------------------------------------------------------------------------------------------------------------------------–----------------------------------------------------------------
Extra information: 
to read the .out file more comprehensibly, we can use a tool called readelf (ELF stands for Executable Linked File)
output of: 
```bash
readelf -S snake | more
```

![image](https://github.com/VoIDWALkER7/Neural-Networks-In-C/blob/main/C%20Concepts/Readelf%20output.png)

 The text of our code ends up in the text section
**rodata** stands for **readonly** data 
--------------------------------------------------------------------------------------------------------------------------------------–
if you write an index that is out of bounds, the C program will still run but it will give random outputs depending on the position of the memory. 

Everytime the array is initiated, we will get a different output of out of bounds index because every time the array is being stored at a different position. 

But, there’s a limit to nonsense, so if we go with an index like 9999 it will give us an error. 

**Segmentaition fault (core dumped)**:
When we try to leave the scope of our program/code i.e leave the memory used by our code, that’s when we encounter the Segmentation Fault. 

Now, to loop through an array, it’s the same procedure like lists: 
```C
int x[] = { 10, 12, 54, 43, 12}; 
int size_x = sizeof(x)/4;

for( int i = 0; i < size_x; i++){
	printf("\n %d", x[i]);

}
```
This is not an ideal solution for determining the length of an array, so we can just divide the sizeof(x) by sizeof(int) but since even this won’t be an universal solution, we can use the following method. 
```C
int x[] = { 10, 12, 54, 43, 12}; 
int size_x = sizeof(x)/sizeof(x[0]);

for( int i = 0; i < size_x; i++){
	printf("\n %d", x[i]);

}
```

Now, we can also use a Macro function which is define as follows: 
```C
#define ARRAY_LEN(x) (sizeof(x) / sizeof(x[0]))
```
So, now our code can be like this: 
```C
#inlcude <stdio.h>
#define ARRAY_LEN(x) (sizeof(x) / sizeof(x[0]))

int main(){
	int x[] = { 10, 12, 54, 43, 12}; 
	
	for( int i = 0; i < size_x; i++){
		printf("\n %d", x[i]);

	}
}

```
[[Comment]](https://github.com/VoIDWALkER7/Neural-Networks-In-C/blob/main/C%20Concepts/Comment.md) <- PREVIOUS
