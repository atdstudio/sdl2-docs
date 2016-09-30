# SDL_Point
A structure that defines a two dimensional point.

该结构定义一个二维点

## Data Fields 字段
|int|**x**|the x coordinate of the point|
|---|-----|-----------------------------|
|int|**y**|the y coordinate of the point|

## Code Examples 代码示例
```c
// Example program:
// Using SDL_Point in some places of your code

#include "SDL.h"
#include <stdio.h>

int main(int argc, char *argv[]) {

    SDL_Window *window;

    SDL_Point window_position = {         //    Position of window
        SDL_WINDOWPOS_CENTERED,
        SDL_WINDOWPOS_CENTERED
    };
    SDL_Point window_size = {640, 480};   //    Size of window

    SDL_Point mouse_position;             //    Mouse position coords

    SDL_Init(SDL_INIT_VIDEO);             //    Initialize SDL2

    // Create an application window with the following settings:
    window = SDL_CreateWindow( 
        "SDL_Point usage",                //    window title
        window_position.x,                //    initial x position
        window_position.y,                //    initial y position
        window_size.x,                    //    width, in pixels
        window_size.y,                    //    height, in pixels
        SDL_WINDOW_OPENGL                 //    flags - see below
    );

    // Check that the window was successfully made
    if (window == NULL) {
        SDL_Log("Could not create window: %s", SDL_GetError());
        return 1;
    }

    SDL_GetMouseState(                    //    Sets mouse_position to...
        &mouse_position.x,                // ...mouse arrow coords on window
        &mouse_position.y
    );

    SDL_Log("Mouse position: x=%i y=%i",  //    Print mouse position
         mouse_position.x, mouse_position.y
    );

    // Close and destroy the window
    SDL_DestroyWindow(window); 

    // Clean up
    SDL_Quit();
    return 0; 
}
```
## Remarks 注意
An [SDL_Point](./SDL_Point.md) defines single two dimensional point. It can be used not only for points, but also for size. [SDL_Point](./SDL_Point.md) is used by [SDL_EnclosePoints()](../Functions/SDL_EnclosePoints.md) to check if array of points is inside rectangle ([SDL_Rect](./SDL_Rect.md)). You can also make your own functions using [SDL_Point](./SDL_Point.md) to simplify your code, it's very helpful.

一个[SDL_Point](./SDL_Point.md)结构定义了一个二维的点。但它不仅可以用来表示点，也可以用来表示大小。[SDL_Point](./SDL_Point.md)也在函数[SDL_EnclosePoints()](../Functions/SDL_EnclosePoints.md)中被用来检查一组点是否在一个矩形([SDL_Rect](./SDL_Rect.md))之内。你也可以在你自己的函数中使用现成的[SDL_Point](./SDL_Point.md)来简化代码，这往往很有用。

## Related Structures 相关结构
[SDL_Rect](./SDL_Rect.md)

## Related Functions 相关函数
[SDL_EnclosePoints()](../Functions/SDL_EnclosePoints.md)
