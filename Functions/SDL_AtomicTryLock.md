
# [SDL_AtomicTryLock](http://wiki.libsdl.org/SDL_AtomicTryLock?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)

Use this function to try to lock a spin lock by setting it to a non-zero value.
使用这个函数设置一个非零值，以试图锁定一个自旋锁。


## Syntax 语法

```c 
SDL_bool SDL_AtomicTryLock(SDL_SpinLock* lock)
```

## Function Parameters 函数参数

| 参数 | 解释(EN) | 解释(ZH) |
|------|----------|---------|
| lock | a pointer to a lock variable | 指向锁的变量。 |


## Return Value 返回值

Returns SDL_TRUE if the lock succeeded, SDL_FALSE if the lock is already held.

如果成功锁定，则返回 SDL_TRUE 函数。如果已经锁定，则返回 SDL_FALSE 函数。


## Code Examples 示例代码

```c 
暂无
```

## Remarks 备注

The atomic locks are efficient spinlocks using CPU instructions, but are vulnerable to starvation and can spin forever if a thread holding a lock has been terminated.
 For this reason you should minimize the code executed inside an atomic lock and never do expensive things like API or system calls while holding them.
这个原子锁是利用CPU指令有效的自旋锁，但是容易受到饥饿并且如果持有锁的线程被终止，那么它将会永远自旋下去。
出于这个原因，你应该尽量减少原子锁内执行的代码，同时保持它们永远不做API或者系统调用。

/!\ The atomic locks are not safe to lock recursively.
原子锁是不是安全的递归锁定。


## Related Functions 相关函数

[SDL_AtomicLock](http://wiki.libsdl.org/SDL_AtomicLock)

[SDL_AtomicUnlock](http://wiki.libsdl.org/SDL_AtomicUnlock)

----------------------------------------------------------------------------------------------------------
*[SixerMe](https://github.com/DXkite) Translated*
