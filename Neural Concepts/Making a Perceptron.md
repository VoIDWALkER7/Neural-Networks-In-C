To make a perceptron, we will require the use of taking inputs from the user, if else statements, and some basic maths. 

Our parameters will be of the float datatype. While input being the char type. Will explain as we go. 

It will consist of the following: 
```C
float p; //perceptron
float threshold;

char input;//input we take from the user

//Better Salary
float x1;
float w1 = 0.8; //weight or importance to the output

//Travel Time
float x2;
float w2 = 0.4;

//More Interesting
float x3;
float w3 = 0.6;

//Better Prospects
float x4;
float w4 = 0.7;

//dissatisfied
float x5;
float w5 = 0.8;

```

So, we are making a program that will determine whether we should be changing our current job to the one job we have been offered or not. 

The parameters for that are: 
1. Better Salary
2. Travel Time
3. More Interesting
4. Better Prospects
5. Disappointed

So, now we will take in the input from the user and based on that input, we will determine the value of the parameter. 
```C
printf("\nDoes the Job have a better salary? ( Y or N )");
scanf(" %c",&input);
	
if(input == 'Y' || input == 'y'){
	x1 = 1;
}
else if(input == 'N' || input == 'n'){
	x1 = 0;
}
else{
	printf("\nINVALID INPUT");
}

```

We will do it in the same manner for all the other parameters:
```C
 //better salary
float x1;
float w1 = 0.8;

char input;

printf("\nDoes the Job have a better salary? ( Y or N )");
scanf(" %c",&input);

if(input == 'Y' || input == 'y'){
	x1 = 1;
}
else if(input == 'N' || input == 'n'){
	x1 = 0;
}
else{
	printf("\nINVALID INPUT");
}


//travel time
float x2;
float w2 = 0.4;

printf("\nDoes the Job have a better travel time? ( Y or N )");
scanf(" %c",&input);

if(input == 'Y' || input == 'y'){
	x2 = 1;
}
else if(input == 'N' || input == 'n'){
	x2 = 0;
}
else{
	printf("\nINVALID INPUT");
}

//more interesting
float x3;
float w3 = 0.6;

printf("\nIs the Job more interesting? ( Y or N )");
scanf(" %c",&input);

if(input == 'Y' || input == 'y'){
	x3 = 1;
}
else if(input == 'N' || input == 'n'){
	x3 = 0;
}
else{
	printf("\nINVALID INPUT");
}

//better prospects
float x4;
float w4 = 0.7;

printf("\nDoes the Job have better prospects? ( Y or N )");
scanf(" %c",&input);

if(input == 'Y' || input == 'y'){
	x4 = 1;
}
else if(input == 'N' || input == 'n'){
	x4 = 0;
}
else{
	printf("\nINVALID INPUT");
}

//dissatisfied
float x5;
float w5 = 0.8;

printf("\nAre you dissatisfied with your current job? ( Y or N )");
scanf(" %c",&input);

if(input == 'Y' || input == 'y'){
	x5 = 1;
}
else if(input == 'N' || input == 'n'){
	x5 = 0;
}
else{
	printf("\nINVALID INPUT");
}
```

Now, we are gonna do some basic mathematics. 
First we are gonna multiple the parameters with their respective weights and then we are gonna add them all together and store them inside the perceptron (p)

```C
p = (x1 * w1) + (x2 * w2) + (x3 * w3) + (x4 * w4) + (x5 * w5);
```

Then we will compare it to the threshold we set previously. 
If the threshold is less than p then you should apply for the job, else you shouldn’t. 
```C
if(p > threshold){
	printf("\n YES: You should apply for the new job.");

}
else{
	printf("\n NO: You shouldn't apply for the new job.");
}
```
OUTPUT:
![image](https://github.com/VoIDWALkER7/Neural-Networks-In-C-Notes/blob/main/Neural%20Concepts/Job%20output.png)

> [!NOTE] Errors Encountered
> When i was typing the inputs, the 2nd and 4th questions won’t register any input and would automatically move to the next questions. 
> This happened because when i typed scanf, during setting up the format of input, i typed “%c” without the space. It led the computer to not understand that it needs to skip whitespaces. So when i added “ %c” instead of the previous one, it started to ignore the whitespaces as it was taking them as inputs automatically and waited for my input.


[[Perceptron]](https://github.com/VoIDWALkER7/Neural-Networks-In-C-Notes/blob/main/Neural%20Concepts/Perceptron.md)<-PREVIOUS

