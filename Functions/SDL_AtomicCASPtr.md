
# [SDL_AtomicCASPtr](http://wiki.libsdl.org/SDL_AtomicCASPtr?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)

Use this function to set a pointer to a new value if it is currently an old value.
使用该函数可以在当前旧值的情况下，为新值设定一个指针。

## Syntax 语法
```c 
切换行号显示
SDL_bool SDL_AtomicCASPtr(void** a,
                          void*  oldval,
                          void*  newval)
```

## Function Parameters 函数参数
| 参数 | 解释(EN) | 解释(ZH) |
| a |  a pointer to a pointer | 一个指针指向另一个指针。 |
| oldval |  the old pointer value | 旧值指针。 |
| newval |   the new pointer value | 新值指针。 |

## Return Value 返回值

Returns SDL_TRUE if the pointer was set, SDL_FALSE otherwise.
如果指针被设定，则返回SDL_TRUE， 否则返回SDL_FALSE.
## Code Examples 示例代码
```c 
暂无
```

## Remarks 注意

{i} Note: If you don't know what this function is for, you shouldn't use it!
{i} 注意：如果你不知道该怎么使用这个函数，那么请不要使用它！
## Version 版本

This function is available since SDL 2.0.0.
这个函数出自 SDL 2.0.0

## Related Functions 相关函数

[SDL_AtomicCAS](http://wiki.libsdl.org/SDL_AtomicCAS)
[SDL_AtomicGetPtr](http://wiki.libsdl.org/SDL_AtomicGetPtr)
[SDL_AtomicSetPtr](http://wiki.libsdl.org/SDL_AtomicSetPtr)

--------------------------------------------------------------------------------------
*@[SixerMe](https://github.com/DXkite) Translated*
