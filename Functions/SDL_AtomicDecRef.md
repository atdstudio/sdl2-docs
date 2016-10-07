# [SDL_AtomicDecRef](http://wiki.libsdl.org/SDL_AtomicDecRef?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)

Use this function to decrement an atomic variable used as a reference count.

使用这个函数可以对原子变量的参考值进行递减操作。

## Syntax 语法
```c 
SDL_bool SDL_AtomicDecRef(SDL_atomic_t* a)
```

## Function Parameters 函数参数
| 参数 | 解释(EN) | 解释(ZH) |
|-----|----------|----------|
| a | a  pointer to an SDL_atomic_t variable to be modified. | 通过指针修改SDL_atomic_t 的变量。 |

## Return Value 返回值

Returns SDL_TRUE if the variable reached zero after decrementing, SDL_FALSE otherwise.
当变量递减为0时，返回SDL_TRUE,否则返回SDL_FALSE。

## Code Examples 示例代码
```c 
暂无
```

## Remarks 注意

暂无

## Related Functions 相关函数

[SDL_AtomicAdd](http://wiki.libsdl.org/SDL_AtomicAdd)

[SDL_AtomicIncRef](http://wiki.libsdl.org/SDL_AtomicIncRef)

-------------------------------------------------------------------------------------
*@[SixerMe](https://github.com/DXkite) Translated*