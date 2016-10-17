# [SDL_AtomicSetPtr](http://wiki.libsdl.org/SDL_AtomicSetPtr?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)


Use this function to set a pointer to a value atomically.

使用这个函数可以为原子指针设置一个值。

## Syntax 语法

```c 
void* SDL_AtomicSetPtr(void** a,
                       void*  v)
```

## Function Parameters 函数参数

| 参数 | 解释(EN) | 解释(ZH) |
|------|----------|---------|
| a | a pointer to a pointer | 指向指针的指针 |
| v | the desired pointer value | 所需的指针值 |


## Return Value 返回值

Returns the previous value of the pointer.

返回指针的前值。

## Code Examples 示例代码

```c 
暂无
```

## Remarks 备注

暂无


## Related Functions 相关函数

[SDL_AtomicCASPtr](http://wiki.libsdl.org/SDL_AtomicCASPtr)

[SDL_AtomicGetPtr](http://wiki.libsdl.org/SDL_AtomicGetPtr)


-----------------------------------------------------------------------------------
*[SixerMe](https://github.com/DXkite) Translated*
