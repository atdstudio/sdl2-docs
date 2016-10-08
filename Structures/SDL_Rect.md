# SDL_Rect
A structure that contains the definition of a rectangle, with the origin at the upper left.该结构定义一个从左上角起始的矩形。
## Data Fields 数据字段
<table>
<tr><td>int</td><td><b>x</b></td><td>the x location of the rectangle's upper left corner</td><td>矩形左上角的x坐标</td></tr>
<tr><td>int</td><td><b>y</b></td><td>the y location of the rectangle's upper left corner</td><td>矩形左上角的y坐标</td></tr>
<tr><td>int</td><td><b>w</b></td><td>the width of the rectangle</td><td>矩形的宽</td></tr>
<tr><td>int</td><td><b>h</b></td><td>the height of the rectangle</td><td>矩形的高</td></tr>
</table>
## Code Examples 示例代码
```C
SDL_Rect srcrect;
SDL_Rect dstrect;

srcrect.x = 0;
srcrect.y = 0;
srcrect.w = 32;
srcrect.h = 32;
dstrect.x = 640/2;
dstrect.y = 480/2;
dstrect.w = 32;
dstrect.h = 32;

SDL_BlitSurface(src, &srcrect, dst, &dstrect);
```
## Remarks 注意
An [SDL_Rect](./SDL_Rect.md) defines a rectangular area of the screen. It is used by [SDL_BlitSurface()](./../Functions/SDL_BlitSurface.md) to define blitting regions and by several other video functions.[SDL_Rect](./SDL_Rect.md)结构在屏幕上定义一个矩形的区域。在[SDL_BlitSurface()](./../Functions/SDL_BlitSurface.md)函数中被用来设置绘制的区域，同时也被很多其他的视频函数所使用。
## Related Functions 相关函数
[SDL_BlitSurface](./../Functions/SDL_BlitSurface.md) 
[SDL_EnclosePoints](./../Functions/SDL_EnclosePoints.md) 
[SDL_GetDisplayBounds](./../Functions/SDL_GetDisplayBounds.md) 
[SDL_HasIntersection](./../Functions/SDL_HasIntersection.md) 
[SDL_IntersectRect](./../Functions/SDL_IntersectRect.md) 
[SDL_LockTexture](./../Functions/SDL_LockTexture.md) 
[SDL_RenderCopy](./../Functions/SDL_RenderCopy.md) 
[SDL_RenderDrawRect](./../Functions/SDL_RenderDrawRect.md) 
[SDL_RenderDrawRects](./../Functions/SDL_RenderDrawRects.md) 
[SDL_RenderReadPixels](./../Functions/SDL_RenderReadPixels.md) 
[SDL_UnionRect](./../Functions/SDL_UnionRect.md) 
[SDL_UpdateTexture](./../Functions/SDL_UpdateTexture.md)

---------------------
Translated by [SteDeshain](http://github.com/SteDeshain)
Reference to http://wiki.libsdl.org/SDL_Rect