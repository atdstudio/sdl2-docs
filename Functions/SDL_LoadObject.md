# SDL_LoadObject
Use this function to dynamically load a shared object and return a pointer to the object handle.
用这个函数可以动态加载一个动态库，并返回动态库的操作句柄

## Syntax 语法

```c
void* SDL_LoadObject(const char* sofile)
```
## Function Parameters 函数相关参数
| 参数名 |解释 |
|--------|-----|
|sofile| a system dependent name of the object file 共享库对象文件名 |

## Return Value

Returns a pointer to the object handle or NULL if there was an error; call  [SDL_GetError](http://wiki.libsdl.org/SDL_GetError) for more information.
返回一个动态库指针，如果出现错误，则返回NULL。调用函数 [SDL_GetError](SDL_GetError.md)() 可获取更多错误信息。  
## Code Examples 代码示例

```c
#include "SDL_loadso.h"

// Dynamically load mylib.so
SDL_LoadObject("mylib.so");
```

## Remarks 注意

> You can add useful comments here 你可以在这里加上有用的注释


##  Related Functions 相关函数

[SDL_LoadFunction](SDL_LoadFunction.md)

[SDL_UnloadObject](SDL_UnloadObject.md)


*@[DXkite](https://github.com/DXkite) Translated.*