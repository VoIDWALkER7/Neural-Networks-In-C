To Generate the apple: 
First, we will create a structure: 
```C
typedef struct{
	int x;
	int y;
} apple;

apple Apple;

```
Now, the following are the functions: 
```C

void gen_apple(){//function to determine the coordinates of the apple
	bool in_snake;

	do{	
		in_snake=false;
		Apple.x = rand() % GRID_SIZE;
		Apple.y = rand() % GRID_SIZE;

		Snake *track = head;

		if(track->x == Apple.x && track->y==Apple.y){
			in_snake=true; //verifying if apple is overlapping with the snake or not
		}
	}while(in_snake);

}

void render_apple(SDL_Renderer *renderer, int x, int y){
		
		SDL_SetRenderDrawColor(renderer, 0xff, 0x00, 0x00, 255);

		int apple_size = GRID_DIM / GRID_SIZE;

		SDL_Rect app;
		app.w = apple_size;
		app.h = apple_size;
		app.x = x + Apple.x * apple_size;
		app.y = y + Apple.y * apple_size;

		SDL_RenderFillRect(renderer, &app);
}

void detect_apple(){
	if(head->x == Apple.x && head->y == Apple.y){
		gen_apple();
		increase_snake(); //increasing the snake after it eats the apple and generating another snake on another coordinates. 
	}
}

```

[[Creating The Snake]](https://github.com/VoIDWALkER7/Neural-Networks-In-C/blob/main/Snake%20Game%20Using%20C%20%26%20SDL2/Creating%20The%20Snake.md) <- PREVIOUS
