# [SDL_AllocFormat](http://wiki.libsdl.org/SDL_AllocFormat?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)
Use this function to create an [SDL_PixelFormat](http://wiki.libsdl.org/SDL_PixelFormat)structure corresponding to a pixel format.
使用这个函数会创建[SDL_PixelFormat](http://wiki.libsdl.org/SDL_PixelFormat)结构来对应每一个像素格式。

## Syntax 语法
```c 
SDL_PixelFormat* SDL_AllocFormat(Uint32 pixel_format)
```

## Function Parameteers 函数参数
|参数名 | 解释（EN） | 解释 ZH |
|---|---|---|
|pixel_format |one of the SDL_PixelFormatEnum values; see Remarks for details.| 其中一个的[SDL_PixelFormatEnum](http://wiki.libsdl.org/SDL_PixelFormatEnum)值; 详情请看[注意](http://wiki.libsdl.org/SDL_AllocFormat#Remarks) . |

## Return Value 返回值
Returns the new [SDL_PixelFormat](http://wiki.libsdl.org/SDL_PixelFormat) structure or NULL on failure; call [SDL_GetError](http://wiki.libsdl.org/SDL_GetError)() for more information.
失败时返回新的[SDL_PixelFormat](http://wiki.libsdl.org/SDL_PixelFormat)结构或者NULL值； 调用[SDL_GetError](http://wiki.libsdl.org/SDL_GetError)会有更多的信息。

## Code Examples 代码示例
```c 
    暂无
```

## Remarks 注意
pixel_format may be one of the following:
|SDL_PIXELFORMAT_UNKNOWN        |               |
|---|:---:|
| SDL_PIXELFORMAT_INDEX1LSB     |               |
| SDL_PIXELFORMAT_INDEX1MSB     |
| SDL_PIXELFORMAT_INDEX4LSB     |
| SDL_PIXELFORMAT_INDEX4MSB     |
| SDL_PIXELFORMAT_INDEX8        |
| SDL_PIXELFORMAT_RGB332        |
| SDL_PIXELFORMAT_RGB444        |
| SDL_PIXELFORMAT_RGB555        |
| SDL_PIXELFORMAT_BGR555        |
| SDL_PIXELFORMAT_ARGB4444      |
| SDL_PIXELFORMAT_RGBA4444      |
| SDL_PIXELFORMAT_ABGR4444      |
| SDL_PIXELFORMAT_BGRA4444      |
| SDL_PIXELFORMAT_ARGB1555      |
| SDL_PIXELFORMAT_RGBA5551      |
| SDL_PIXELFORMAT_ABGR1555      |
| SDL_PIXELFORMAT_BGRA5551      |
| SDL_PIXELFORMAT_RGB565        |
| SDL_PIXELFORMAT_BGR565        |
| SDL_PIXELFORMAT_RGB24         |
| SDL_PIXELFORMAT_BGR24         |
| SDL_PIXELFORMAT_RGB888        |
| SDL_PIXELFORMAT_RGBX8888      |
| SDL_PIXELFORMAT_BGR888        | 
| SDL_PIXELFORMAT_BGRX8888      |
| SDL_PIXELFORMAT_ARGB8888      |
| SDL_PIXELFORMAT_RGBA8888      | 
| SDL_PIXELFORMAT_ABGR8888      |
| SDL_PIXELFORMAT_BGRA8888      |
| SDL_PIXELFORMAT_ARGB2101010   |
| SDL_PIXELFORMAT_YV12          |       planar mode: Y + V + U (3 planes)  |
| SDL_PIXELFORMAT_IYUV          |       planar mode: Y + U + V (3 planes)  |
| SDL_PIXELFORMAT_YUY2          |       packed mode: Y0+U0+Y1+V0 (1 plane) |
| SDL_PIXELFORMAT_UYVY          |       packed mode: U0+Y0+V0+Y1 (1 plane) |
| SDL_PIXELFORMAT_YVYU          |       packed mode: Y0+V0+Y1+U0 (1 plane  |

Returned structure may come from a shared global cache (i.e not newly allocated), and hence should not be modified, esspecially the palette. Wwird errors such as Bilit combination not supported may coour.
返回结构可能来自一个共享的全局缓存(即不分配)，因此不应该修改，特别是调色板。可能会出现奇怪的组合，如BLIT不支持。

## Related Function 相关函数
[SDL_FreeFormat](http://wiki.libsdl.org/SDL_FreeFormat)

-----------------------------------------------------------------------
*@[SixerMe](https://github.com/DXkite) Translated*
