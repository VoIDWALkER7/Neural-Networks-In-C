To create a grid, we will create a function in the code from the previous page and name is as render_grid. 
The parameters that will go in there are the renderer value, the coordinates where you want the grid to be. 
```C
void render_grid(SDL_Renderer *renderer, int x, int y){  
       SDL_SetRenderDrawColor(renderer, 0x55, 0x55, 0x55, 255);  
       int cell_size = GRID_DIM/ GRID_SIZE; 
       SDL_Rect cell;  
       cell.w = cell_size;  
       cell.h = cell_size;  
       for(int i = 0; i < GRID_SIZE; i++){  
               for(int j=0;j<GRID_SIZE;j++){  
                       cell.x = x + (i * cell_size);  
                       cell.y = y + (j * cell_size);  
                       SDL_RenderDrawRect(renderer, &cell);  
               }  
       }  
       return;  
}
```
In the above code, we have defined the GRID_SIZE and GRID_DIM ( DIMENSION ) beforehand only. 
```C
#define GRID_SIZE 20
#define GRID_DIM 800 //dimensions
```
in the above code, we have used :
- SDL_SetRenderDrawColor to set the color of the grid to gray. 
- we have set the cell size to 40 (800/20)
- we have used the SDL_Rect to define our grid’s cell. SDL_Rect stands for Rectangle/ 
- cell.w & cell.h stands for cell width, and cell height respectively. 
- We have then used for loop to keep placing the cells at different coordinates throughout the plane. i changes the rows, while j changes the columns. 
Output:
![image](https://github.com/VoIDWALkER7/Neural-Networks-In-C/blob/main/Snake%20Game%20Using%20C%20%26%20SDL2/Grid.png)

Now, to center it, we will do the follows: 
```C
int grid_x = (WINDOW_WIDTH/ 2) - (GRID_DIM / 2);
int grid_y = (WINDOW_HEIGHT/ 2) - (GRID_DIM / 2);
```
![image](https://github.com/VoIDWALkER7/Neural-Networks-In-C/blob/main/Snake%20Game%20Using%20C%20%26%20SDL2/Centered%20Grid.png)

To expand the grid we can just change the GRID_DIM and GRID_WIDTH accordingly. 

[[SDL2]](https://github.com/VoIDWALkER7/Neural-Networks-In-C/blob/main/Snake%20Game%20Using%20C%20%26%20SDL2/SDL2.md) ← PREVIOUS

NEXT → [[Creating The Snake]](https://github.com/VoIDWALkER7/Neural-Networks-In-C/blob/main/Snake%20Game%20Using%20C%20%26%20SDL2/Creating%20The%20Snake.md)
