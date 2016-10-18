# [SDL_AtomicUnlock](http://wiki.libsdl.org/SDL_AtomicUnlock?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)


Use this function to unlock a spin lock by setting it to 0.
使用这个函数可以将值设为0，以解锁一个自旋锁。

## Syntax 语法

```c 
void SDL_AtomicUnlock(SDL_SpinLock* lock)
```

## Function Parameters 函数参数


| 参数 | 解释(EN) | 解释(ZH) |
|------|----------|----------|
| lock | a pointer to a lock variable.| 指向锁的变量。|


## Code Examples 示例代码

```c 
暂无
```

## Remarks 备注


Always returns immediately.

总是立即返回。


## Version 版本

This function is available since SDL 2.0.0.
函数出自SDL2.0.0

# Related Functions 相关函数

[SDL_AtomicLock](http://wiki,libsdl.org/SDL_AtomicLock)

[SDL_AtomicTryLock](http://wiki.libsdl.org/SDL_AtomicTryLock)

---------------------------------------------------------------------------
*[SixerMe](https://github.com/DXkite) Translated*
