- Linux kernel uses MakeFiles
- Makefiles are used to make our work faster while compiling the code and multiple files
- It is used to automate the compilation process for a particular application. 
- Make file will run the commands inside by simply using the command make
- The following is an example of makefile
```Makefile
	CFLAGS = -Wno-implicit-function-declaration
	
	all:final
	
	final: main.o hello.o
		@echo "Compiling the final application"
		gcc $(CFLAGS) main.o hello.o -o final
		chmod +x final
	main.o: main.c
		@echo "Compiling the main files"
		gcc $(CFLAGS) -c main.c
	hello.o: hello.c
		@echo "Compiling the hello files"
		gcc $(CFLAGS) -c hello.c
	clean:
		@echo "Removing all but source"
		rm main.o hello.o final	
		
```
- CFLAGS are the flags that are used with the gcc compiler
- all: final: hello.h: main.h: are the functions to compile the files accordingly.
- clean: is used to clean all the files except the source files. 
- @ is used to hide the commands from the output and just execute them. 
