# SDL_RenderSetViewport
Use this function to set the drawing area for rendering on the current target.使用该函数可以为当前渲染目标上的渲染操作设置绘制区域。
## Syntax 语法
```C
int SDL_RenderSetViewport(SDL_Renderer*   renderer,
                          const SDL_Rect* rect)
```
## Function Parameters 函数参数
<table>
<tr><td><b>renderer</b></td><td>the rendering context</td><td>渲染器</td></tr>
<tr><td><b>rect</b></td><td>the <a herf = "./../Structures/SDL_Rect.md">SDL_Rect</a> structure representing the drawing area, or NULL to set the viewport to the entire target</td><td>表示绘制区域的<a herf = "./../Structures/SDL_Rect.md">SDL_Rect</a>结构，或者为NULL以表示绘制区域为整个渲染目标</td></tr>
</table>
## Return Value 返回值
Returns 0 on success or a negative error code on failure; call <a herf = "./SDL_GetError.md">SDL_GetError()</a> for more information.执行成功返回0,执行失败则返回一个负的错误码，调用<a herf = "./SDL_GetError.md">SDL_GetError()</a>以获得更多的错误信息。
## Code Examples 示例代码
```C
暂无
```
## Remarks 注意
When the window is resized, the current viewport is automatically centered within the new window size.当窗口重新调整大小后，当前的绘制区域也会自动调整至新的窗口尺寸的中央。
## Related Functions 相关函数
[SDL_RenderGetViewport](./SDL_RenderGetViewport.md)

---------------------
translated by [SteDeshain](https://github.com/SteDeshain)
Reference to [http://wiki.libsdl.org/SDL_RenderSetViewport](http://wiki.libsdl.org/SDL_RenderSetViewport?highlight=%28%5CbCategoryRender%5Cb%29%7C%28CategoryEnum%29%7C%28CategoryStruct%29)