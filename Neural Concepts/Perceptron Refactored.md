We are coding the previous perceptron we coded and are making it better. 
I will be directly pasting the code below and then after that will be explaining the functions used and concepts used in the code. 
```C 
#include <stdio.h>
#include <string.h>

#define THRESHOLD 1.6
#define INPUT_COUNT 5

int set_input(int i, char input_buff, float *input){
	
	if(input_buff == 'Y' || input_buff == 'y'){
		*input = 1;
	}
	else if(input_buff == 'N' || input_buff == 'n'){
		*input = 0;
		if(i==3){
			printf("\n \t Well, get ready to lose your sleep!\n");
		}
	}
	else{
		return -1;
	}
	return 0;
}

void *get_questions(int i, float *weight){ //* represents string literal function
	switch(i){
		case 0:
			*weight = 0.8;
			return "Do you love to create new things?";
			break;
		case 1: 
			*weight = 0.6;
			return "Do you love to learn new things continuously?";
			break;
		case 2: 
			*weight = 0.4;
			return "Are you willing to give up your social life?";
			break;
		case 3: 
			*weight = 0.4;
			return "Do you have insomnia?";
			break;
		case 4: 
			*weight = 0.7;
			return "Are you patient enough to search for bugs for hours?";
			break;
		default:
			return "ERROR";
			break;
	}

}

int main()
{
	printf("----------Should you choose computer science as your major?---------\n");

	float x[INPUT_COUNT];
	float w[INPUT_COUNT];
	
	float p;
	float p_max;
	char input;

	for(int i = 0; i<INPUT_COUNT; i++){
		char *str = get_questions(i,&w[i]);
		
		if(!strcmp("ERROR",str)){
			fprintf(stderr, "\nERROR: No Questions Defined. Check The Questions.");
			return 1;
		}

		printf("\t %s (Y or N):", str);

		scanf(" %c",&input);
		while(getchar() != '\n');
	
		if( set_input(i,input,&x[i]) != 0){
			fprintf(stderr, "ERROR: INVALID OUTPUT");
			return 1;
		}
		
		p += x[i] * w[i];
		p_max += 1*w[i];
	}
	if(p<THRESHOLD){
		printf("\t\033[1;31mNO: Choose Design\033[0m");
	}
	else{
		printf("\t\033[1;32mYES: You can choose Computer Science\033[0m");
	}

	printf("\n\t%%P = %f%%", (p/p_max)*100);
	
	return 0;

}
```

So, first, we have set macro here: 
```C
#define THRESHOLD 1.6
#define INPUT_COUNT 5
```
Wherever the respective macro is mentioned, it will be replaced by the value written in front of it. 

Now, we have created two functions, so let’s talk about them later, first let’s talk about the main function:
```C
int main()
{
	printf("----------Should you choose computer science as your major?---------\n");

	float x[INPUT_COUNT];
	float w[INPUT_COUNT];
	
	float p;
	float p_max;
	char input;

	for(int i = 0; i<INPUT_COUNT; i++){
		char *str = get_questions(i,&w[i]);
		
		if(!strcmp("ERROR",str)){
			fprintf(stderr, "\nERROR: No Questions Defined. Check The Questions.");
			return 1;
		}

		printf("\t %s (Y or N):", str);

		scanf(" %c",&input);
		while(getchar() != '\n');
	
		if( set_input(i,input,&x[i]) != 0){
			fprintf(stderr, "ERROR: INVALID OUTPUT");
			return 1;
		}
		
		p += x[i] * w[i];
		p_max += 1*w[i];
	}
	if(p<THRESHOLD){
		printf("\t\033[1;31mNO: Choose Design\033[0m");
	}
	else{
		printf("\t\033[1;32mYES: You can choose Computer Science\033[0m");
	}

	printf("\n\t%%P = %f%%", (p/p_max)*100);
	
	return 0;

}
```

first we have created to arrays: 
```C
	float x[INPUT_COUNT];
	float w[INPUT_COUNT];
```
it will take in our have our inputs and weights respectively stored in the arrays. 
we have also created variables for the perceptron(p), the maxiumum value the perceptron can hold(p_max),  and the character variable input for taking in answers like yes or no. 
after that, it’s a for loop and at the beginning of it, I have used the string.h library’s strcmp. 

```C
char *str = get_questions(i,&w[i]);
		
		if(!strcmp("ERROR",str)){
			fprintf(stderr, "\nERROR: No Questions Defined. Check The Questions.");
			return 1;
		}
```
So, what this does it, if the get_questions function returns “ERROR” as a string, then the if statement will compare the output from the get_questions to “ERROR” and if they both are the same thing, it will return the output that says ERROR": No questions defined.” and then return 1 as the exit code which denotes that the program didn’t run how it was supposed to run. 

After this part, we are taking the input according to the questions that will be printed by the get_questions function(that’s the only task of that function asides for assigning weights to parameters). 

Now the following line of code: 
```C
while(getchar() != '\n');
```
This line of code ensures that the loop doesn’t move forward till you haven’t pressed enter after typing the input. 
so in case you type ‘Y’ 5 times, instead of answering for all the questions, with this code, it will answer only for one of them. 

```C
if( set_input(i,input,&x[i]) != 0){
			fprintf(stderr, "ERROR: INVALID OUTPUT");
			return 1;
		}
```
Now, the above line of code, will see if the exit code from the function set_input(function to determine whether x will be 0 or 1) is anything other than 1. if it is, then it will throw out this error. 

```C
p += x[i] * w[i];
p_max += 1*w[i];
```
This line just adds the product of input and weight to the perceptron variable and also adds max weight value to p_max to calculate the percentage later on. 

Now, let’s understand the functions: 
```C
void *get_questions(int i, float *weight){ // '*' before represents string literal function
	switch(i){
		case 0:
			*weight = 0.8;
			return "Do you love to create new things?";
			break;
		case 1: 
			*weight = 0.6;
			return "Do you love to learn new things continuously?";
			break;
		case 2: 
			*weight = 0.4;
			return "Are you willing to give up your social life?";
			break;
		case 3: 
			*weight = 0.4;
			return "Do you have insomnia?";
			break;
		case 4: 
			*weight = 0.7;
			return "Are you patient enough to search for bugs for hours?";
			break;
		default:
			return "ERROR";
			break;
	}

}
```
This functions takes in the value of i from the for loop and the address of the weight. 
It returns the questions based on what the value of i is. 
The value of i is passed through the switch cased and then the question is returned and weight value is entered inside the weight array. 
When the value of i is not present in the switch case, it goes to the default case and returns “ERROR”, which is then sent to strcmp and throws the stderr and ends the program. 

Now, let’s move on to the other function:
```C
int set_input(int i, char input_buff, float *input){
	
	if(input_buff == 'Y' || input_buff == 'y'){
		*input = 1;
	}
	else if(input_buff == 'N' || input_buff == 'n'){
		*input = 0;
		if(i==3){
			printf("\n \t Well, get ready to lose your sleep!\n");
		}
	}
	else{
		return -1;
	}
	return 0;
}
```

This functions takes in the value of i from for loop, the input that user has entered (Y or N), and the x[i] variable’s address which is the actual input in the form of 0 or 1. 

If the input is Y or y, then the *input = 1 else it’s 0. 

Also, just for the sake of a joke, in case i is 3, which is the i for the question that asks the user if they have insomnia, the function will output that they should be prepared to lose their sleep. 

also, in case the input that the user enters is neither Y/y nor  N/n it will throw an error which will go to the if statement that checks if the exit code is 0 or not and in case it’s not, it will output Error: invalid output. 

Now, let’s move to the final part of the code: 
```C
if(p<THRESHOLD){
	printf("\t\033[1;31mNO: Choose Design\033[0m");
}
else{
	printf("\t\033[1;32mYES: You can choose Computer Science\033[0m");
}

printf("\n\t%%P = %f%%", (p/p_max)*100);

return 0;
```

this is the final piece of code, so in case p is less than the threshold, which we have present to be 1.6, then it will tell the user to choose design instead of CS. But, there’s an addition, it will say that in red color. 
similarly, if it’s equal or more than the threshold, it will tell the user that they can choose computer science but in green. 
the color is being determined by the following part. 
```C
"\033[1;32m text \033[0m" //1;32 -> GREEN
"\033[1;31m text   \033[0m" //1;31 -> RED
```

Now, to compile the code you just run:
```bash
gcc percep-refac.c
```
and to run the code after that, you run:
```bash
./a.out
```

[[Making a Perceptron]] ← PREVIOUS