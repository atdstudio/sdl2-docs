
# [SDL_AtomicSet](http://wiki.libsdl.org/SDL_AtomicSet?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)


Use this function to set an atomic variable to a value.

使用这个函数可以设置原子变量的值。


## Syntax 语法
```c 
int SDL_AtomicSet(SDL_atomic_t* a,
                  int           v)
```

## Function Parameters 函数参数
| 参数 | 解释(EN) | 解释(ZH) |
|------|---------|----------|
| a | a pointer to an SDL_atomic_t variable to be modified. | 指向要修改的 SDL_atomic_t 的变量。| 
| v | the desired value. | 预期值。 |


## Return Value 返回值

Returns the previous value of the atomic variable.

返回原子变量的前值。


## Code Examples 示例代码
```c 
暂无
```

## Remarks 备注

This function also acts as a full memory barrier.

这个函数也可以作为完全内存屏障。


## Related Functions 相关函数

[SDL_AtomicGet](http://wiki.libsdl.org/SDL_AtomicGet)


----------------------------------------------------------------------------------
*[SixerMe](https://github.com/DXkite)  Translated*