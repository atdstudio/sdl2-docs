#[SDL_SetAssertionHandler](https://wiki.libsdl.org/SDL_SetAssertionHandler)
Use this function to set an application-defined assertion handler.

使用该函数设置一个应用程序指定的断言处理函数。

##Syntax 语法
```C
void SDL_SetAssertionHandler(SDL_AssertionHandler handler, void* userdata)
```

##Function Parameters 函数参数

<table>
<tr><td><b>handler</b></td><td>the function to call when an assertion fails or NULL for the default handler; see <a href="#remarks-注释">Remarks</a> for details.<br/>
当断言失败时要调用的函数或者填入NULL使用默认的处理函数。<a href="#remarks-注释">注释</a>中有详细说明。</td></tr>
<tr><td><b>userdata</b></td><td>a pointer that is passed to <b>handler</b>.<br/>
传入到<b>处理函数</b>的数据指针。</td></tr>
</table>

##Code Examples 代码示例
```
暂无。
```

##Remarks 注释
This function allows an application to show its own assertion UI and/or force the response to an assertion failure. If the application doesn't provide this, SDL will try to do the right thing, popping up a system-specific GUI dialog, and probably minimizing any fullscreen windows.

该函数允许应用程序显示它自己的断言界面和/或强制断言的回应失败。如果程序中没有指定，SDL 会尝试做正确的行为，弹出一个系统特定的对话框，并且尝试最小化所有全屏的窗口。

The function prototype for **handler** is:

**handler** 的函数原型是：
```C
SDL_AssertState YourAssertionHandler(const SDL_AssertData* data, void* userdata)
```

>where `YourAssertionHandler` is the name of your function and its parameters are:

>其中 `YourAssertionHandler` 是你声明的函数名字，参数为：

><table>
<tr><td>data</td><td>a pointer to the <a href="../Structures/SDL_AssertData">SDL_AssertData</a> structure corresponding to the current assertion<br/>
一个用来表示当前断言的 <a href="../Structures/SDL_AssertData">SDL_AssertData</a> 结构体指针。</td></tr>
<tr><td>userdata</td><td>what was passed as <b>userdata</b> to <a href="SDL_SetAssertionHandler.md">SDL_SetAssertionHandler</a>()<br/>
传入 <a href="SDL_SetAssertionHandler.md">SDL_SetAssertionHandler</a>() 中作为 <b>userdata</b> 参数的数据指针。</td></tr>
</table>

>This callback should return an [SDL_AssertState](../Enumerations/SDL_AssertState.md) value indicating how to handle the assertion failure.

>该回调函数应返回一个用于表示如何处理断言失败的 [SDL_AssertState](../Enumerations/SDL_AssertState.md) 值。

This callback may fire from any thread, but it runs wrapped in a mutex, so it will only fire from one thread at a time.

该回调函数可能会从任何线程触发，但由于它是在互斥体中封装的，所以一次只会从一个线程中触发。

This callback is NOT reset to SDL's internal handler upon [SDL_Quit](SDL_Quit.md)()!

该函数不会因调用 [SDL_Quit](SDL_Quit.md)() 而被重置为 SDL 的内部处理函数。

##Related Functions 相关函数

[SDL_GetAssertionHandler](SDL_GetAssertionHandler.md)

---
@[lxfly2000](https://github.com/lxfly2000)
