# [SDL_AtomicLock](http://wiki.libsdl.org/SDL_AtomicLock?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)

Use this function to lock a spin lock by setting it to a non-zero value.
使用这个函数将其设置为非零值以锁定自旋锁。

## Syntax 语法
```c 
void SDL_AtomicLock(SDL_SpinLock* lock)
```

## Function Parameters 函数参数
| 参数 | 解释(EN) | 解释(ZH) |
|------|----------|---------|
| lock | a pointer to a lock variable | 指向自旋锁的变量。|

## Code Examples 示例代码
```c 
暂无
```

## Remarks 备注

The atomic locks are efficient spinlocks using CPU instructions, but are vulnerable to starvation and can spin forever if a thread holding a lock has been terminated.
For this reason you should minimize the code executed inside an atomic lock and never do expensive things like API or system calls while holding them.
这个原子锁是利用CPU有效指令的自旋锁，但是很消耗资源并且如果一个线程持有的锁被终止，那么它就永远自旋下去。
出于这个原因，你应该减少原子锁内的执行代码同时保持他们永远不会做消耗资源的操作。

/!\ The atomic locks are not safe to lock recursively.
这个原子锁是不是安全的递归锁定。

## Related Functions 相关函数

[SDL_AtomicTryLock](http://wiki.libsdl.org/SDL_AtomicTryLock)
[SDL_AtomicUnlock](http://wiki.libsdl.org/SDL_AtomicUnlock)

--------------------------------------------------------------
*[SixerMe](https://github.com/DXkite) Translated*
