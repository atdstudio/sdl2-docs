# [SDL_AllocPalette](http://wiki.libsdl.org/SDL_AllocPalette?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)

Use this function to create a palette structure with the specified number of color entries.
 使用这个函数创建一个调色板结构，与指定数量的颜色项。

 ## Syntax 语法
 ```c 
SDL_Palette* SDL_AllocPalette(int ncolors)
 ```

## Function Parameters 函数参数
| 参数 | 解释(EN) | 解释(ZH) |
|-----|-----|-----|
| ncolors | represents the number of color rntrise in the color palette. | 在调色板上代表颜色的条目。|

## Return Value 返回值
Retuen a new [SDL_Palette](http://wiki.libsdl.org/SDL_Palette) structure on success or NULL on failure(e.g. if there wasn't enough memory); call [SDL_GetError](http://wiki.libsdl.org/SDL_GetError)()for more information.
如果成功就返回一个新的 [SDL_Palette](http://wiki.libsdl.org/SDL_Palette) 结构，如果失败就返回NULL(例如，没有足够的内存)；调用[SDL_GetError](http://wiki.libsdl.org/SDL_GetError)()查看更多信息。

## Code Examples 代码示例
```c 
暂无
```

## Remarks 注意
The palette entries are initialized to white.
调色板的主实话颜色是白色。

## Related Function 相关函数
[SDL_FreePalette](http://wiki.libsdl.org/SDL_FreePalette)

------------------------------------------------------------------------------------
*@[SixerMe](https://github.com/DXkite) Translated.*