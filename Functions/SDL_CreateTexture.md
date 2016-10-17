# SDL_CreateTexture
Use this function to create a texture for a rendering context.   
使用该函数可以为特定渲染器创造一个纹理。
## Syntax 语法   
``` C
SDL_Texture* SDL_CreateTexture(SDL_Renderer* renderer,
                               Uint32        format,
                               int           access,
                               int           w,
                               int           h)
```   
## Function Parameters 函数参数   

<table>
<tr><td><b>renderer</b></td><td>the rendering context</td><td>渲染器</td></tr>
<tr><td><b>format</b></td><td>one of the enumerated values in <a href = "./../Enumerations/SDL_PixelFormatEnum.md">SDL_PixelFormatEnum</a>; see <a href = "#remarks-注意">Remarks</a> for details</td><td><a href = "./../Enumerations/SDL_PixelFormatEnum.md">SDL_PixelFormatEnum</a>枚举中的一个值，参考<a href = "#remarks-注意">Remarks</a>以获取详细信息</td></tr>
<tr><td><b>access</b></td><td>one of the enumerated values in <a href = "./../Enumerations/SDL_TextureAccess.md">SDL_TextureAccess</a>; see <a href = "#remarks-注意">Remarks</a> for details</td><td><a href = "./../Enumerations/SDL_TextureAccess.md">SDL_TextureAccess</a>枚举中的一个值，参考<a href = "#remarks-注意">Remarks</a>以获取详细信息</td></tr>
<tr><td><b>w</b></td><td>the width of the texture in pixels</td><td>该纹理的宽度，以像素为单位</td></tr>
<tr><td><b>h</b></td><td>the height of the texture in pixels</td><td>该纹理的高度，以像素为单位</td></tr>
</table>   

## Return Value 返回值   
Returns a pointer to the created texture or NULL if no rendering context was active, the format was unsupported, or the width or height were out of range; call [SDL_GetError()](./../Functions/SDL_GetError.md) for more information.   
返回一个指针指向被创造的纹理，但如果没有活动的渲染器，或者format格式不被支持，或者宽度或高度超过限度，则返回NULL，调用[SDL_GetError()](./../Functions/SDL_GetError.md)以获取更多的错误信息。
## Code Examples 代码示例   
```C
#include "SDL.h"

/* Moving Rectangle 移动的矩形*/
int main(int argc, char *argv[])
{
        SDL_Window *window;
        SDL_Renderer *renderer;
        SDL_Texture *texture;
        SDL_Event event;
        SDL_Rect r;

        if (SDL_Init(SDL_INIT_VIDEO) < 0) {
                SDL_LogError(SDL_LOG_CATEGORY_APPLICATION, "Couldn't initialize SDL: %s", SDL_GetError());
                return 3;
        }

        window = SDL_CreateWindow("SDL_CreateTexture",
                        SDL_WINDOWPOS_UNDEFINED,
                        SDL_WINDOWPOS_UNDEFINED,
                        1024, 768,
                        SDL_WINDOW_RESIZABLE);

        r.w = 100;
        r.h = 50;

        renderer = SDL_CreateRenderer(window, -1, 0);

        texture = SDL_CreateTexture(renderer, SDL_PIXELFORMAT_RGBA8888, SDL_TEXTUREACCESS_TARGET, 1024, 768);

        while (1) {
                SDL_PollEvent(&event);
                if(event.type == SDL_QUIT)
                        break;
                r.x=rand()%500;
                r.y=rand()%500;

                SDL_SetRenderTarget(renderer, texture);
                SDL_SetRenderDrawColor(renderer, 0x00, 0x00, 0x00, 0x00);
                SDL_RenderClear(renderer);
                SDL_RenderDrawRect(renderer,&r);
                SDL_SetRenderDrawColor(renderer, 0xFF, 0x00, 0x00, 0x00);
                SDL_RenderFillRect(renderer, &r);
                SDL_SetRenderTarget(renderer, NULL);
                SDL_RenderCopy(renderer, texture, NULL, NULL);
                SDL_RenderPresent(renderer);
        }
        SDL_DestroyRenderer(renderer);
        SDL_Quit();
        return 0;
}
```   
## Remarks 注意   
format may be one of the following:   
参数format可以是以下值中的一个：   

<table>
<tr><td>SDL_PIXELFORMAT_UNKNOWN</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_INDEX1LSB</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_INDEX1MSB</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_INDEX4LSB</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_INDEX4MSB</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_INDEX8</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_RGB332</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_RGB444</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_RGB555</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_BGR555</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_ARGB4444</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_RGBA4444</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_ABGR4444</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_BGRA4444</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_ARGB1555</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_RGBA5551</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_ABGR1555</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_BGRA5551</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_RGB565</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_BGR565</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_RGB24</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_BGR24</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_RGB888</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_RGBX8888</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_BGR888</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_BGRX8888</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_ARGB8888</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_RGBA8888</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_ABGR8888</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_BGRA8888</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_ARGB2101010</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_RGBA32</td><td>alias for RGBA byte array of color data, for the current platform (>= SDL 2.0.5)</td></tr>
<tr><td>SDL_PIXELFORMAT_ARGB32</td><td>alias for ARGB byte array of color data, for the current platform (>= SDL 2.0.5)</td></tr>
<tr><td>SDL_PIXELFORMAT_BGRA32</td><td>alias for BGRA byte array of color data, for the current platform (>= SDL 2.0.5)</td></tr>
<tr><td>SDL_PIXELFORMAT_ABGR32</td><td>alias for ABGR byte array of color data, for the current platform (>= SDL 2.0.5)</td></tr>
<tr><td>SDL_PIXELFORMAT_YV12</td><td>planar mode: Y + V + U (3 planes)</td></tr>
<tr><td>SDL_PIXELFORMAT_IYUV</td><td>planar mode: Y + U + V (3 planes)</td></tr>
<tr><td>SDL_PIXELFORMAT_YUY2</td><td>packed mode: Y0+U0+Y1+V0 (1 plane)</td></tr>
<tr><td>SDL_PIXELFORMAT_UYVY</td><td>packed mode: U0+Y0+V0+Y1 (1 plane)</td></tr>
<tr><td>SDL_PIXELFORMAT_YVYU</td><td>packed mode: Y0+V0+Y1+U0 (1 plane)</td></tr>
<tr><td>SDL_PIXELFORMAT_NV12</td><td>planar mode: Y + U/V interleaved (2 planes) (>= SDL 2.0.4)</td></tr>
<tr><td>SDL_PIXELFORMAT_NV21</td><td>planar mode: Y + V/U interleaved (2 planes) (>= SDL 2.0.4)</td></tr>
</table>

access may be one of the following:   
参数access可以是以下值中的一个：

<table>
<tr><td>SDL_TEXTUREACCESS_STATIC</td><td>changes rarely, not lockable</td><td>纹理几乎不会改变，不可被锁定</td></tr>
<tr><td>SDL_TEXTUREACCESS_STREAMING</td><td>changes frequently, lockable</td><td>纹理经常会改变，可以被锁定</td></tr>
<tr><td>SDL_TEXTUREACCESS_TARGET</td><td>can be used as a render target</td><td>纹理可以作为渲染目标</td></tr>
</table>

You can set the texture scaling method by setting [SDL_HINT_RENDER_SCALE_QUALITY](./../Hints/SDL_HINT_RENDER_SCALE_QUALITY.md) before creating the texture.   
在创造纹理之前，你可以设置[SDL_HINT_RENDER_SCALE_QUALITY](./../Hints/SDL_HINT_RENDER_SCALE_QUALITY.md)的值来设定纹理的缩放质量。
## Related Functions 相关函数
[SDL_CreateTextureFromSurface](./SDL_CreateTextureFromSurface.md)   
[SDL_DestroyTexture](./SDL_DestroyTexture.md)   
[SDL_QueryTexture](./SDL_QueryTexture.md)   
[SDL_UpdateTexture](./SDL_UpdateTexture.md)   

---
Translated by [SteDeshain](https://github.com/SteDeshain)   
Reference to http://wiki.libsdl.org/SDL_CreateTexture