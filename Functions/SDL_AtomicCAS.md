# [SDL_AtomicCAS](http://wiki.libsdl.org/SDL_AtomicCAS?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)

Use this function to set an atmoic variable to a new value if it is currently an old value.
使用该函数可以对当前的原子变量旧值更改为新值。
## Syntax 语法
```c 
SDL_bool SDL_AtomicCAS(SDL_atomic_t*    a,
                        int         oldval,
                        int         newval)
```

## Function Parameters 函数参数
| 参数 | 解释（EN）| 解释(ZH) |
|-----|----------|----------|
| a | a pinter to an [SDL_atomic_t](http://wiki.libsdl.org/SDL_atomic_t) variable to be modified.| 指向 [SDL_atomic_t](http://wiki.libsdl.org/SDL_atomic_t) 并修改它的参数。 |
| oldval | the old value | 旧值 | 
| newval | the new value | 新值 |

## Return Value 返回值
Return SDL_TRUE if the atmoic variable was set , SDL_FAILSE otherwise.
如果对原子变量成功赋值，则返回SDL_TRUE, 否则返回SDL_FAILSE。
## Code Examples 示例代码
```c 
暂无
```

## Remarks 注意
Note: If you don't know waht this function is for,you shoulen't use it.
注意：如果你不知道怎么使用这个函数的话， 请慎重使用。
## Version 版本
This function is available since SDL 2.0.0
这个函数出自 SDL 2.0.0
## Related Function 相关函数
[SLD_AtomicCASPtr](http://wiki.libsdl.org/SDL_AtomicCASPtr)
[SDL_AtomicGet]((http://wiki.libsdl.org/SDL_AtomicGet)
[SDL_AtomicSet]((http://wiki.libsdl.org/SDL_AtomicSet)

----------------------------------------------------------------------
*@[SixerMe](https://github.com/DXkite) Translated*