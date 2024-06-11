## Primitives
- Different types data types: 
	- **int** - size 4 bytes ( Whole Numbers)
	- **short int** - size 2 bytes ( here’s the reason why it’s called short int, it requires less space than int. ) 
	- **long int** - size 8 bytes ( here’s the reason why it’s called long it, it requires twice the space than int, and four times than that of short int)
	- **float** - size 4 bytes ( Fractions)
	- **char** - size 1 byte (Characters)
	- **double** - size 8 bytes ( It’s an extension of float, and well, it takes more space than that. )
	- **long double** - size 16 bytes ( well, extension of double, and you know why it’s long. )
 - 
![image](https://github.com/VoIDWALkER7/Neural-Networks-In-C/blob/main/C%20Concepts/Data%20Types%20Size.png)

## Binary
- The numbers we usually know of our base 10. Base 10 means there are basically 10 unique symbols that can be used to generate numbers or alphabets using ascii system, or basically anything. 
- For base 10, we can divide the numbers using the concept of 1s, 10s, 100s, for example, in case of 101, we can do the following: 

| 100s | 10s | 1s |
|:----:|:---:|:--:|
|    3|   0 |  1 |  

- For binary, we use Base 2. Basically, it means we only have 2 symbols to use to generate characters & numbers. The two symbols are: 0 and 1. 
- For eg: unlike Base 10, we don’t use the concept of 1s, 10s & 100s. Instead, we go up by a factor of 2, always. Let’s take 101 as an example.  

| $$2^2$$ | $$2^1$$ | $$2^0$$|
|:----:|:---:|:--:|
|    1|   0 |  1 |

To calculate what 101 mean, we will just multiply the number that is inside the column with the column identifier ( the 2s) and then, we will add all of them. So, in this case.  $$101 = 2^{2}* 1 + 2^{1}*0 + 2^{0}* 1 = 4 + 0 + 1 = 5$$
More examples like that: 

| $$2^2$$ | $$2^1$$ | $$2^0$$|
|:----:|:---:|:--:|
|    1|   1 |  1 |

$$111 = 2^{2}* 1 + 2^{1*1}+ 2^{0 * 1}= 4 + 2 + 1 = 7$$
##### What is a byte?
- 8 bits
- The range for that 1 byte or 8 bits can store is from 0 - 255 (00000000 → 0, 11111111→ 255), i.e 256 values. But, this is for unsigned data types. 
- For signed data type, the range is from -128 to 127. 
- If you increase the byte size by one, the following is the result: 
	- Unsigned Range → 0 to 65,535, Signed Range → -32,728 to +32767
	- This is the case for short int. 
###### What is a bit?
- The number of columns that are used to store the binary value. For eg:
	- For 5, the binary is 101. According to the table, it took 3 bits to store 5.
#### ASCII Table
![image](https://github.com/VoIDWALkER7/Neural-Networks-In-C/blob/main/C%20Concepts/ASCII%20Table.png)

[[Basic Syntax & Formatting]](https://github.com/VoIDWALkER7/Neural-Networks-In-C/blob/main/C%20Concepts/Basic%20Syntax%20%26%20Formatting.md) ← PREVIOUS

NEXT → [[Operators]](https://github.com/VoIDWALkER7/Neural-Networks-In-C/blob/main/C%20Concepts/Operators.md)
