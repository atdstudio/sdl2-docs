#[SDL_AssertState](https://wiki.libsdl.org/SDL_AssertState)
An enumeration of assertion handling states.

断言处理状态的枚举。

##Values 值

<table>
<tr><td>SDL_ASSERTION_RETRY</td><td>retry the assert immediately</td><td>立刻重试断言</td></tr>
<tr><td>SDL_ASSERTION_BREAK</td><td>trigger a breakpoint under the debugger</td><td>在调试器中触发断点</td></tr>
<tr><td>SDL_ASSERTION_ABORT</td><td>terminate the program</td><td>终止程序</td></tr>
<tr><td>SDL_ASSERTION_IGNORE</td><td>ignore the assert</td><td>忽略断言</td></tr>
<tr><td>SDL_ASSERTION_ALWAYS_IGNORE</td><td>ignore the assert from now on</td><td>从现在开始一直忽略断言</td></tr>
</table>

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
