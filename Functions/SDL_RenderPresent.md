# SDL_RenderPresent
Use this function to update the screen with any rendering performed since the previous call.   
使用该函数可以把自从上次调用以来的所有渲染操作都更新到屏幕上。
## Syntax 语法
```C
void SDL_RenderPresent(SDL_Renderer* renderer)
```
## Function Parameters 函数参数

<table>
<tr><td><b>renderer</b></td><td>the rendering context</td><td>渲染器</td></tr>
</table>

## Code Examples 代码示例
```C
#include "SDL.h"

int main(int argc, char* argv[])
{
        SDL_Window* window;
        SDL_Renderer* renderer;

        /* Initialize SDL. */
		/* 初始化SDL */
        if (SDL_Init(SDL_INIT_VIDEO) < 0)
                return 1;

        /* Create the window where we will draw. */
		/* 创造窗口用来绘画 */
        window = SDL_CreateWindow("SDL_RenderClear",
                        SDL_WINDOWPOS_CENTERED, SDL_WINDOWPOS_CENTERED,
                        512, 512,
                        0);

        /* We must call SDL_CreateRenderer in order for draw calls to affect this window. */
		/* 必须先调用SDL_CreateRenderer，才可以执行这个窗口上的绘制操作 */
        renderer = SDL_CreateRenderer(window, -1, 0);

        /* Select the color for drawing. It is set to red here. */
		/* 选择绘制的颜色，这里我们选择红色 */
        SDL_SetRenderDrawColor(renderer, 255, 0, 0, 255);

        /* Clear the entire screen to our selected color. */
		/* 用我们选择的颜色来清空整个屏幕 */
        SDL_RenderClear(renderer);

        /* Up until now everything was drawn behind the scenes.
           This will show the new, red contents of the window. */
		/* 到目前为止所有的绘制都没有画到屏幕上。这个操作会在整个屏幕上显示红色 */
        SDL_RenderPresent(renderer);

        /* Give us time to see the window. */
		/* 延迟显示我们才能看到窗口 */
        SDL_Delay(5000);

        /* Always be sure to clean up */
		/* 记得每次都要做清理工作 */
        SDL_Quit();
        return 0;
}
```
## Remarks 注意
SDL's rendering functions operate on a backbuffer; that is, calling a rendering function such as SDL_RenderDrawLine() does not directly put a line on the screen, but rather updates the backbuffer. As such, you compose your entire scene and present the composed backbuffer to the screen as a complete picture.   
SDL的渲染函数都是在一个缓冲区上进行的，也就是说，比如调用SDL_RenderDrawLine()，并不会直接在屏幕上绘制一条直线，而是会更新到那个缓冲区。所以这样一来，你要先组合好整个场景，然后把绘制好的缓冲区作为一整个图片来显示到屏幕上。

Therefore, when using SDL's rendering API, one does all drawing intended for the frame, and then calls this function once per frame to present the final drawing to the user.   
因此，当使用SDL的渲染API中的函数时，先在一帧中绘制好所有要绘制的，然后再在每一帧中都调用该函数，才能为用户呈现最终的画面。

The backbuffer should be considered invalidated after each present; do not assume that previous contents will exist between frames. You are strongly encouraged to call [SDL_RenderClear()](./SDL_RenderClear.md) to initialize the backbuffer before starting each new frame's drawing, even if you plan to overwrite every pixel.   
在每一次显示后，缓冲区都应该被认为失效了。在两帧之间，不要假设前一次显示的画面仍然存在。所以，强烈建议你在每一帧开始时绘制时，都要调用[SDL_RenderClear()](./SDL_RenderClear.md)来初始化缓冲区，甚至就算你打算重新复写每一个像素，也应该调用那个函数。
## Related Functions 相关函数
[SDL_RenderClear](./SDL_RenderClear.md)   
[SDL_RenderDrawLine](./SDL_RenderDrawLine.md)   
[SDL_RenderDrawLines](./SDL_RenderDrawLines.md)   
[SDL_RenderDrawPoint](./SDL_RenderDrawPoint.md)   
[SDL_RenderDrawPoints](./SDL_RenderDrawPoints.md)   
[SDL_RenderDrawRect](./SDL_RenderDrawRect.md)   
[SDL_RenderDrawRects](./SDL_RenderDrawRects.md)   
[SDL_RenderFillRect](./SDL_RenderFillRect.md)   
[SDL_RenderFillRects](./SDL_RenderFillRects.md)   
[SDL_SetRenderDrawBlendMode](./SDL_SetRenderDrawBlendMode.md)   
[SDL_SetRenderDrawColor](./SDL_SetRenderDrawColor.md)   

---
Translated by [SteDeshain](https://github.com/SteDeshain)   
Reference to http://wiki.libsdl.org/SDL_RenderPresent