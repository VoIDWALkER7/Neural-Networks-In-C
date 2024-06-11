The library that hosts SDL is SDL.h.
The first thing we do in SDL programming is create a window. 
```C
SDL_Window *window;
SDL_Renderer *renderer;
```
we can use surfaces instead of render as well because we can use hardware acceleration. 
```C
if(SDL_INIT_VIDEO < 0){
	fprintf(stderr, "ERROR: SDL_INIT_VIDEO");
}
window = SDL_CreateWindow(
	"Snake",
	WINDOW_X,
	WINDOW_Y,
	WINDOW_WIDTH,
	WINDOW_HEIGHT,
	SDL_WINDOW_BORDERLESS
)
```
- SDL_Init is uses to initialize the SDL video subsystem.
- fprintf is used to print error messages to stderr
- SDL_CreateWindow is used to create a window with the title of snake and the specified positions and dimensions

we will define the WINDOW_X, WINDOW_Y, WINDOW_WIDTH, WINDOW_HEIGHT before the main function. 

```C
#define WINDOW_X 0
#define WINDOW_Y 0
#define WINDOW_HEIGHT 1000
#define WINDOW_WIDTH 1000
```
the define keyword is used to define environment variables for the C program. 
```C
if(!window){
	fprintf(stderr, "ERROR: !window");
}

renderer = SDL_CreateRenderer(window, -1, SDL_RENDERER_ACCELERATED);

if(!renderer){
	fprintf(stderr, "ERROR: !renderer");
}

SDL_SetRenderDrawColor(renderer, 0x00, 0xff, 0x00, 255);
SDL_RenderClear(renderer);
SDL_RenderPresent(renderer);
SDL_Delay(2000);

SDL_DestroyRenderer(renderer);
SDL_DestroyWindow(window);
SDL_Quit();
```
- SDL_CreateRenderer is used to create a renderer for the window
- SDL_SetRenderDrawColor to set the color to green 
- SDL_RenderClear to clear the renderer
- SDL_RenderPresent to present the renderer
- SDL_Delay is used like sleep here to wait for 2 second before quitting
- SDL_DestroyWindow to destroy the window
- SDL_DestroyRenderer to destroy the renderer
- SDL_Quit to quit the SDL video subsystem
The following code is to be used in case you are getting a transparent window.  
```C
Unit32 startMs = SDL_GetTicks();
while (SDL_GetTicks() - startMs < 5000) {  
               SDL_PumpEvents(); //updates the function queue 
  
               // Render something  
               SDL_RenderSetLogicalSize(renderer, 1000, 1000);  
  
               // Set the color of the renderer  
               SDL_SetRenderDrawColor(renderer, 255, 0, 0, 255);  
  
               // Clear the screen to the set color  
               SDL_RenderClear(renderer);  
  
               // Show all that has been done behind the scenes  
               SDL_RenderPresent(renderer);  
       }

SDL_DestroyRenderer(renderer);
        SDL_DestroyWindow(window);
        SDL_Quit();


```

what this code will do is, it will wait till 5 seconds before closing the window. 
now, we want it to exit after we press a certain key, so we will modify the code in the following way:
```C

bool quit = false;  
SDL_Event event;
while (!quit){
	while (SDL_PollEvent(&event)) {
			SDL_PumpEvents();

			// Render something
			SDL_RenderSetLogicalSize(renderer, 1000, 1000);

			// Set the color of the renderer
			SDL_SetRenderDrawColor(renderer, 255, 0, 0, 255);

			// Clear the screen to the set color
			SDL_RenderClear(renderer);

			// Show all that has been done behind the scenes
			SDL_RenderPresent(renderer);

			switch(event.type){
				case SDL_QUIT:
						quit = true;
						break;
				case SDL_KEYUP:
						break;
				case SDL_KEYDOWN:
					switch(event.key.keysym.sym){
						case SDLK_ESCAPE:
							quit = true;
							break;
					}
			}
	}
}

```
in this code, we have used SDL_Event
- quit is a bool value that is set to false initially, and then we have a loop that follows around that.
- SDL_PollEvent(&event) function polls events if there’s an event and returns 1, else it returns 0. 
- SDL_PumpEvents functions updates the event queue, but the code works well without it as well, because we are now using  SDL_Event, that is able to keep track of the events. 
- SDL_QUIT is the case where you press on the X button in the title bar to quit the app
- SDL_KEYUP is the case where no key is being pressed
- SDL_KEYDOWN is the case where a key is being pressed, now inside that case we have another switch case, which represents the case SDLK_ESCAPE, which is the case in which the Esc key is being pressed. it will lead to the exit of the application.


NEXT –> [[Creating a Grid]](https://github.com/VoIDWALkER7/Neural-Networks-In-C/blob/main/Snake%20Game%20Using%20C%20%26%20SDL2/Creating%20a%20Grid.md)
