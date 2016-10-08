# [SDL_AtomicGetPtr](http://wiki.libsdl.org/SDL_AtomicGetPtr?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)

Use this function to get the value of a pointer atomically.
使用这个函数获取原子指针的值。

Syntax
```c 
void* SDL_AtomicGetPtr(void** a)
```

## Function Parameters 函数参数
| 参数 | 解释(EN) | 解释(ZH) |
|------|----------|---------|
| a | a pointer to a pointer | 指向原子变量的指针。 |

## Return Value 返回值

Returns the current value of a pointer.
返回指针的当前值。

## Code Examples 示例代码
```c 
暂无
```

## Remarks 备注

暂无

## Related Functions 相关函数

[SDL_AtomicCASPtr](http://wiki.libsdl.org/SDL_AtomicCASPtr)
[SDL_AtomicSetPtr](http://wiki.libsdl.org/SDL_AtomicSetPtr)

-----------------------------------------------------------------------
*@[SixerMe](https://github.com/DXkite) Translated*
