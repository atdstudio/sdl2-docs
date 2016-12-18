# [SDL_BlitSurface](http://wiki.libsdl.org/SDL_BlitSurface?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)

Use this function to perform a fast surface copy to a destination surface. 

使用这个函数可以快速的将表面复制到目标表面。

## Syntax 语法

```c 
int SDL_BlitSurface(SDL_Surface*    src,
                    const SDL_Rect* srcrect,
                    SDL_Surface*    dst,
                    SDL_Rect*       dstrect)
```

## Function Parameters 函数参数
| 参数 | 解释(EN) | 解释(ZH) |
|------|---------|----------|
| src | the [SDL_Surface](wiki.libsdl.org/SDL_Surface)() structure to be copied from | 要复制的[SDL_Surface](wiki.libsdl.org/SDL_Surface)()结构。|
| srcrect | the [SDL_Rect](wiki.libsdl.org/SDL_Rect)() structure representing the rectangle to be copied, or NULL to copy the entire surface | [SDL_Rect](wiki.libsdl.org/SDL_Rect)()结构表示要复制的矩形。或者NULL 来复制整个表面。|
| dst | the [SDL_Surface](wiki.libsdl.org/SDL_Surface)() structure that is the blit target | 作为blit目标的SDL_Surface结构。|
| dstrect | the [SDL_Rect](wiki.libsdl.org/SDL_Rect)() structure representing the rectangle that is copied into | [SDL_Rect](wiki.libsdl.org/SDL_Rect)() 表示被复制到的矩形。|


##　Return Value 返回值

Returns 0 if the blit is successful or a negative error code on failure; call [SDL_GetError](wiki.libsdl.org/SDL_GetError)() for more information. 

如果blit成功就返回数值0，失败则返回负的错误代码；调用[SDL_GetError](wiki.libsdl.org/SDL_GetError)()查看更多信息。

## Code Examples 示例代码

```c 
SDL_BlitSurface(surface, &source_rect, temp_surface, NULL);
```

##　Remarks　备注

You should call [SDL_BlitSurface](wiki.libsdl.org/SDL_BlitSurface)() unless you know exactly how SDL blitting works internally and how to use the other blit functions. 

除非你知道如何准确的使用SDL blitting 的内部工程和怎样使用其他的blit 函数，否则你应该调用[SDL_BlitSurface](wiki.libsdl.org/SDL_BlitSurface).

This is the public blit function, and it performs rectangle validation and clipping before passing it to [SDL_LowerBlit](wiki.libsdl.org/SDL_LowerBlit)(). 

这个公共的blit函数，裁剪后传递给[SDL_LowerBlit](wiki.libsdl.org/SDL_LowerBlit)()并执行矩形验证.

The blit function should not be called on a locked surface. 

不应在锁定表面上调用blit函数。

The width and height in srcrect determine the size of the copied rectangle. Only the position is used in the dstrect (the width and height are ignored). Blits with negative dstrect coordinates will be clipped properly.

srcrect的宽度和高度决定了复制的矩形大小，只在位置中使用 dstrect (高度和宽度忽略。)Blits 与 负的 dstrect 坐标将正确剪辑。

If srcrect is NULL, the entire surface is copied. If dstrect is NULL, then the destination position (upper left corner) is (0, 0). 

如果 srcrect 是 NULL 值，那么就完整的复制。如果 dstrect 是 NULL 值，那么目标的位置（左上角）是 （0，0）.

The final blit rectangle is saved in dstrect after all clipping is performed (srcrect is not modified). 

经过剪辑和执行之后，blit 矩形将保存在 dstrect 中。（srcrect 不能修改。 ）

The blit semantics for surfaces with and without blending and colorkey are defined as follows:

具有和不具有混合和colorkey的表面的blit语义定义如下：

RGBA->RGB: 

        Source surface blend mode set to SDL_BLENDMODE_BLEND:

        alpha-blend (using the source alpha-channel and per-surface alpha) SDL_SRCCOLORKEY ignored.

        Source surface blend mode set to SDL_BLENDMODE_NONE: 
    
        copy RGB. if SDL_SRCCOLORKEY set, only copy the pixels matching the RGB values of the source color key, ignoring alpha in the comparison. 
RGB->RGBA: 

        Source surface blend mode set to SDL_BLENDMODE_BLEND:

        alpha-blend (using the source per-surface alpha) 

        Source surface blend mode set to SDL_BLENDMODE_NONE: 

        copy RGB, set destination alpha to source per-surface alpha value. 

        both: if SDL_SRCCOLORKEY set, only copy the pixels matching the source color key. 
RGBA->RGBA: 

        Source surface blend mode set to SDL_BLENDMODE_BLEND: 

        alpha-blend (using the source alpha-channel and per-surface alpha) SDL_SRCCOLORKEY ignored. 

        Source surface blend mode set to SDL_BLENDMODE_NONE: 

        copy all of RGBA to the destination. if SDL_SRCCOLORKEY set, only copy the pixels matching the RGB values of the source color key, ignoring alpha in the comparison. 
RGB->RGB: 

        Source surface blend mode set to SDL_BLENDMODE_BLEND: 
    
        alpha-blend (using the source per-surface alpha) 

        Source surface blend mode set to SDL_BLENDMODE_NONE: 
        
        copy RGB. 
        
        both: if SDL_SRCCOLORKEY set, only copy the pixels matching the source color key. 


##  Related Functions 相关函数

[SDL_BlitScaled](wiki.libsdl.org/SDL_BlitScaled)()

[SDL_LowerBlit](wiki.libsdl.org/SDL_LowerBlit)()

---------------------------------------
*[SixerMe](https://github.com/DXkite) Translated*
