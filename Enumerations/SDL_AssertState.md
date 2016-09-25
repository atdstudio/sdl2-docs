#[SDL_AssertState](https://wiki.libsdl.org/SDL_AssertState)
An enumeration of assertion handling states.

断言处理状态的枚举。

##Values 值

| SDL_ASSERTION_RETRY| retry the assert immediately 立刻重试断言|
|SDL_ASSERTION_BREAKtrigger a breakpoint under the debugger 在调试器中触发断点|
|SDL_ASSERTION_ABORTterminate the program 终止程序|
|SDL_ASSERTION_IGNOREignore the assert 忽略断言|
|SDL_ASSERTION_ALWAYS_IGNOREignore the assert from now on 从现在开始一直忽略断言|

##Code Examples 代码示例
```
暂无。
```

##Remarks 注释
This enumeration is returned by the callback function in SDL_SetAssertionHandler() to determine the response to failed assertions.

该枚举是由回调函数 [SDL_SetAssertionHandler](../Functions/SDL_SetAssertionHandler.md)() 返回，用来决定断言失败时的回应。

##Related Functions 相关函数
[SDL_SetAssertionHandler](../Functions/SDL_SetAssertionHandler.md)

---
@[lxfly2000](https://github.com/lxfly2000)
