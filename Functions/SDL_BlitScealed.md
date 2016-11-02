
#[SDL_BlitScaled](http://wiki.libsdl.org/SDL_BlitScaled?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)

Use this function to perform a scaled surface copy to a destination surface.

使用这个函数可以使缩放表面复制到目标表面。

## Syntax 语法

```c 
int SDL_BlitScaled(SDL_Surface*    src,
                   const SDL_Rect* srcrect,
                   SDL_Surface*    dst,
                   SDL_Rect*       dstrect)
```

## Function Parameters 函数参数

|   参数   | 解释(EN) | 解释(ZH) |
|---------|----------|---------|
|    src  | the [SDL_Surface](http;//wiki.libsdl.org/SDL_Suface)() structure to be copied from | 从[SDL_Surface](http;//wiki.libsdl.org/SDL_Surface)() 结构复制。|
| srcrect |  the [SDL_Rect](http;//wiki.libsdl.org/SDL_Rect)() structure representing the rectangle to be copied, or NULL to copy the entire surface | 表示整个矩形[SDL_Rect](http;//wiki.libsdl.org/SDL_Rect)()都要被复制，或者用NULL来辅助整个表面。
|   dst   | the [SDL_Surface](http;//wiki.libsdl.org/SDL_Surface)() structure that is the blit target | [SDL_Surface](http;//wiki.libsdl.org/SDL_Surface)()的结构是blit的目标。
| dstrect | the [SDL_Rect](http;//wiki.libsdl.org/SDL_Rect)() structure representing the rectangle that is copied into, or NULL to copy into the entire surface | [SDL_Rect](http;//wiki.libsdl.org/SDL_Rect)() 结构表示被复制到的矩形，或者用NULL来复制整个目标。


## Return Value 返回值

Returns 0 on success or a negative error code on failure; call SDL_GetError() for more information.

成功则返回0，失败则返回为负的错误代码;调用[SDL_GetError](wiki.libsdl.org/SDL_GetError)()查看更多信息。

## Code Examples 示例代码

```c 
暂无
```

## Remarks 备注

This is the public scaled blit function. This function calls [SDL_LowerBlitScaled](wiki.libsdl.org//SDL_LowerBlitScaled)() internally.

这个是公共的缩放blit函数，这个函数调用内部的[SDL_LowerBlitScaled](wiki.libsdl.org/SDL_LowerBlitScaled)().

## Related Functions 相关函数

[SDL_BlitSurface](wiki.;ibsdl.org/SDL_BlitSurface)()

[SDL_LowerBlitScaled](wiki.libssdl.org/SDL_LowerBlitScaled)()

--------------------------------------------------

*[SixerMe](https://github.com/DXkite)  Translated.*