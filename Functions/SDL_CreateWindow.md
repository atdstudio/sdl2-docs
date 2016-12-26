#### SDL_CreateWindow

Use this function to create a window with the specified position, dimensions, and flags.


使用此函数来创建与指定的位置，尺寸和标志的窗口。

#### Syntax **语法** 

```
SDL_Window* SDL_CreateWindow(const char* title, 2 int x, 3 int y, 4 int w, 5 int h, 6 Uint32 flags) 
```
#### Function Parameters **函数参数** 
| Header | Header |
|:----------:|:----------:|
|   title    |    the title of the window, in UTF-8 encoding    |   该窗口的标题，在UTF-8编码
|   x   |    the x position of the window, SDL_WINDOWPOS_CENTERED, or SDL_WINDOWPOS_UNDEFINED    |    窗口的x位置SDL_WINDOWPOS_CENTERED或SDL_WINDOWPOS_UNDEFINED
|   y   |the y position of the window, SDL_WINDOWPOS_CENTERED, or SDL_WINDOWPOS_UNDEFINED    |     窗口的y位置，SDL_WINDOWPOS_CENTERED或SDL_WINDOWPOS_UNDEFINED
|   w   |   the width of the window, in screen coordinates    |    窗口的宽度，在屏幕坐标
|   h   |   the height of the window, in screen coordinates   |    该窗口的高度，在屏幕坐标
|   flags   |    0, or one or more SDL_WindowFlags OR'd together; see Remarks for details    |    0，或一个或多个SDL_WindowFlags逻辑或运算，; 见备注详情

#### Return Value **返回值** 

Returns the window that was created or NULL on failure; call SDL_GetError() for more information.
 
返回已失败创建或NULL的窗口; 调用SDL_GetError（）了解更多信息。

#### Code Examples **** 

```
// Example program:
 // Using SDL2 to create an application window 
#include "SDL.h"
 #include <stdio.h>
 int main(int argc, char* argv[]) 
{
 SDL_Window *window; 
// Declare a pointer SDL_Init(SDL_INIT_VIDEO); 
// Initialize SDL2 初始化sdl2
// Create an application window with the following settings: 创建一个包含以下设置应用程序窗口
window = SDL_CreateWindow( 
        "An SDL2 window", 
// window title
        SDL_WINDOWPOS_UNDEFINED,
// initial x position初始化x位置
        SDL_WINDOWPOS_UNDEFINED,
 // initial y position 初始化y位置
        640,
 // width, in pixels 以480个像素为宽度
        480, 
// height, in pixels 
       SDL_WINDOW_OPENGL
 // flags - see below 标识flags参见下文
     ); 
     // Check that the window was successfully created检查窗口创建成功
 if (window == NULL) { 
      // In the case that the window could not be made... 在这种情况下窗口不能…
printf("Could not create window: %s\n", SDL_GetError()); 
return 1;
 } 
    // The window is open: could enter program loop here (see SDL_PollEvent())
 SDL_Delay(3000); 
    // Pause execution for 3000 milliseconds, for example暂停执行3000毫秒
     // Close and destroy the window关闭销毁窗口
 SDL_DestroyWindow(window);
     // Clean up 清理
SDL_Quit(); 
return 0;
 }

 ```

#### Remarks **备注** 

flags may be any of the following OR'd together:

标志可以是下列任何逻辑与的一起：


| Header | Header |
|:----------:|:----------:|
|SDL_WINDOW_FULLSCREEN   |    fullscreen window    |    全屏窗口
|    SDL_WINDOW_FULLSCREEN_DESKTOP    |   fullscreen window at the current desktop resolution    |    在目前的桌面分辨率全屏窗口
|     SDL_WINDOW_OPENGL    |    window usable with OpenGL context    |    窗口的OpenGL上下文可用
|    SDL_WINDOW_HIDDEN    |    window is not visible    |    窗口不可见
|    SDL_WINDOW_BORDERLESS    |     no window decoration    |    没有窗户的修饰
 |    SDL_WINDOW_RESIZABLE    |    window can be resized    |    窗口可以调整大小
|    SDL_WINDOW_MINIMIZED    |    window is minimized    |     窗口最小化
|    SDL_WINDOW_MAXIMIZED    |    window is maximized   |    窗口最大化
|    SDL_WINDOW_INPUT_GRABBED  | window has grabbed input focus    |    窗口有抢下输入焦点
|    SDL_WINDOW_ALLOW_HIGHDPI        |    window should be created in high-DPI mode if supported (>= SDL 2.0.1)    |    窗口应在高DPI模式创建如果支持的话（> = 2.0.1 SDL）

SDL_WINDOW_SHOWN is ignored by SDL_CreateWindow(). The SDL_Window is implicitly shown if SDL_WINDOW_HIDDEN is not set. SDL_WINDOW_SHOWN may be queried later usingSDL_GetWindowFlags().

SDL_WINDOW_SHOWN被忽略SDL_CreateWindow（）。被隐式所示的SDL_Window如果未设置SDL_WINDOW_HIDDEN。SDL_WINDOW_SHOWN可在以后通过查询SDL_GetWindowFlags（）。

On Apple's OS X you must set the NSHighResolutionCapable Info.plist property to YES, otherwise you will not receive a High DPI OpenGL canvas.

在苹果的OS X，你必须设置NSHighResolutionCapable的Info.plist属性为YES，否则您将不会收到一个高DPI的OpenGL画布。

If the window is created with the SDL_WINDOW_ALLOW_HIGHDPI flag, its size in pixels may differ from its size in screen coordinates on platforms with high-DPI support (e.g. iOS and Mac OS X). Use SDL_GetWindowSize() to query the client area's size in screen coordinates, and SDL_GL_GetDrawableSize() orSDL_GetRendererOutputSize() to query the drawable size in pixels.

 如果与SDL_WINDOW_ALLOW_HIGHDPI标志创建的窗口，它的像素大小可以从它的大小不同的屏幕上使用高DPI支持的平台坐标（如iOS和Mac OS X的）。使用SDL_GetWindowSize（）来查询客户区的大小在屏幕坐标，和SDL_GL_GetDrawableSize（）或SDL_GetRendererOutputSize（）来查询可绘像素尺寸。

If the window is set fullscreen, the width and height parameters w and h will not be used. However, invalid size parameters (e.g. too large) may still fail. Window size is actually limited to 16384 x 16384 for all platforms at window creation. 

如果设置了窗口全屏，宽度和高度参数瓦特和ħ将不被使用。然而，无效的尺寸参数（例如过大）仍可能会失败。窗口大小实际上是限制在16384点¯x16384在窗口创建的所有平台。

#### Version **版本** 

This function is available since SDL 2.0.0.

#### Related Functions **相关函数** 

[SDL_CreateWindowFrom](http://wiki.libsdl.org/SDL_CreateWindowFrom)
[SDL_DestroyWindow](http://wiki.libsdl.org/SDL_DestroyWindow)

---
*@[PomeloSan](https://github.com/PomeloSan) Translated .*