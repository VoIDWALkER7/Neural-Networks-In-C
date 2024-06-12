If else is an important concept in the world of programming. We use it to verify some condition to run a block of code, whether it be to set a value to a variable on the basis of what the input is, or if the output of the previous block of code matches with the requirements or not. 

Example: 
If you are above 18, you can vote, else you cannot. 

^ If we were to write the above statement in C code, the following syntax will be followed: 

```C
if (age >= 18){
	eligibility = True;
}
else{
	eligibility = False;
}

```

Except if else, there is another statement that is a part of this. 
it’s called else if statement. It’s used in cases where there are more than one possible condition that can be met and result in different outputs/scenarios accordingly. 

Example: 
```C
if(name == 'Trek'){
	printf("You are part of the group");
}
else if(name == 'Troy'){
	printf("Nope, you are banned");
}
else{
	printf("You need to give a test to get in");
}
```
There can be many else if statements in a if else block but only one if and else statement will be there dictating the start and the end of the block. 

[[Inputs]](https://github.com/VoIDWALkER7/Neural-Networks-In-C-Notes/blob/main/C%20Concepts/Inputs.md) ← PREVIOUS

NEXT → [[Arrays]](https://github.com/VoIDWALkER7/Neural-Networks-In-C-Notes/blob/main/C%20Concepts/Arrays.md)
