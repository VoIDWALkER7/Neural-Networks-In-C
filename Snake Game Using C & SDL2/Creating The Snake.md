To create the snake first we will create a structure called snake:
```C
struct snake{
 int x;//x-cordinate
 int y;//y-cordinate
 int dir;//direction
 struct snake *next;//pointer to the next segment of the snake
};typedef struct snake Snake
```
structure is used to create a data type that is capable of being merged with different data types. 
the next pointer is to point to the next segment of the snake so that it can be placed accordingly and rendered accordingly. 
typedef is used to define a new name for the data type, like here struct snake has a new name Snake. 
```C
enum{
	SNAKE_UP,
	SNAKE_DOWN,
	SNAKE_RIGHT,
	SNAKE_LEFT
}
```
 the above block of code is an enumeration to define data types in C. Used to assign names to integral constants for the code to be easier to read and maintain. 
 then we will define head and tail pointers. 
 ```C
 Snake *head;//pointer to the head
 Snake *tail;//pointer to the tail
```
now, to initialize, increase the size and render the snake. 
```C
void init_snake(){
        Snake *new = malloc(sizeof(Snake)); // Allocate memory for a new snake
        new->x = rand() % (GRID_SIZE /2) + (GRID_SIZE/4); // Set the x-coordinate of the snake
        new->y = rand() % (GRID_SIZE /2) + (GRID_SIZE/4); // Set the y-coordinate of the snake
        new->dir = SNAKE_UP; // Set the direction of the snake
        new->next = NULL; // Set the next pointer to NULL

        head = new; // Set the head of the snake
        tail = new; // Set the tail of the snake

        return;
}

// Function to increase the size of the snake
void increase_snake(){
        Snake *new = malloc(sizeof(Snake)); // Allocate memory for a new snake
        new->x = tail->x; // Set the x-coordinate of the new snake
        new->y = tail->y -1; // Set the y-coordinate of the new snake
        new-> dir = tail-> dir; // Set the direction of the new snake
        new-> next = NULL; // Set the next pointer to NULL
        tail -> next = new; // Add the new snake to the tail of the existing snake

        tail = new; // Update the tail of the snake
        return;
}

// Function to render the snake
void render_snake(SDL_Renderer *renderer){
        SDL_SetRenderDrawColor(renderer, 0x00, 0xff, 0x00, 255); // Set the color of the snake
        int seg_size = GRID_DIM / GRID_SIZE; // Calculate the size of a segment
        SDL_Rect seg; // Define a rectangle for a segment
        seg.w = seg_size; // Set the width of the segment

        Snake *track = head; // Start from the head of the snake
        while (track != NULL){ // Loop through each segment of the snake
                seg.x = x + track-> x * seg_size; // Set the x-coordinate of the segment
                seg.y = y + track-> y * seg_size; // Set the y-coordinate of the segment

                SDL_RenderFillRect(renderer, &seg); // Render the segment
                track = track->next; // Move to the next segment
        }
}
```
![image](https://github.com/VoIDWALkER7/Neural-Networks-In-C/blob/main/Snake%20Game%20Using%20C%20%26%20SDL2/Rendered%20Snake.png)

the above snake is after the increase_size function was run 3 times. 

There are other functions as well: 
```C
void move_snake(){
	int prev_x = head->x; //marking the initial position of the head's x axis
	int prev_y = head->y; //marking the initial position of the head's y axis
	int prev_dir = head->dir; //marking the previous direction the head was heading into

	switch(head->dir){
		case SNAKE_UP:
			head->y--; //reducing the Y axis to move the snake up
			break;
		case SNAKE_DOWN:
			head->y++; //increasing the Y axis to move the snake down
			break;
		case SNAKE_LEFT:
			head->x--; //decreasing the X axis to move the snake left
			break;
		case SNAKE_RIGHT:
			head->x++; //increasing the X axist to move the snake right
			break;
	}
	Snake *track = head; //setting the track on the head
	if(track->next != NULL){
		track=track->next;
	}

	while(track!=NULL){
		int save_x = track->x; //saving the current position of the head's x axis
		int save_y = track->y; //saving the current position of head's y axis
		int save_dir = track->dir; //saving the current positon of head's direction

//tracking the previous position of the head
		track->x = prev_x; 
		track->y = prev_y;
		track->dir = prev_dir;
	
		track=track->next; //now it moves to the next track to store new information in the later part of the loop in the next node. 
		//the new position is now saved in the previous variables
		prev_x = save_x;
		prev_y = save_y;
		prev_dir = save_dir;
	}
}

```

[[Creating a Grid]](https://github.com/VoIDWALkER7/Neural-Networks-In-C/blob/main/Snake%20Game%20Using%20C%20%26%20SDL2/Creating%20a%20Grid.md) <- PREVIOUS
