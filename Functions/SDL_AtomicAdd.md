# [SDL_AtomicAdd](http://wiki.libsdl.org/SDL_AtomicAdd?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)

User this function to add to an atomic variable.
这个函数是添加原子变量。

## Syntax 语法
```c 
int SDL_AtomicAdd(SDL_atomic_t* a,
                 int            v)
```

## Function  Parameters 函数参数
| 参数 | 解释(EN) | 解释(ZH) |
|-----|----------|----------|
| a | a pointer to an SDL_atomic_t variable to be modified | 通过指针对SDL_atomic_t 的变量进行修改。 |
| v | the desired value to add | 想添加的值 |

## Return Value 返回值
Return the previous value of the atomic variable.
返回原子原子变量的前值。

## Code Examples 示例代码
```c 
暂无
```

## Remarks 注意
This function also acts as a full memory barrier.
该函数还可以充当完全内存屏障。

## Related Functions 相关函数 

[SDL_AtomicDecRef](http://wiki.libsdl.org/SDL_AtomicDecRef)
[SDL_AtomicIncRef](http://wiki.libsdl.org/SDL_AtomicIncRef)

-----------------------------------------------------------------------------------------------------------
*@[SixerMe](https://github.com/DXkite) Translated*