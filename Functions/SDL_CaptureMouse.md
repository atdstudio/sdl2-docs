

# [SDL_CaptureMouse](http;//libsdl.org/SDL_CaptureMouse)

Use this function to capture the mouse and to track input outside an SDL window.

使用这个函数可以获取鼠标和SDL窗口之外的轨道输入。

## Syntax 语法

```c 
int SDL_CaptureMouse(SDL_bool enabled)
```

## Function Parameters 函数参数

| 参数 | 解释（EN） | 解释（ZH） |
|------|-----------|-----------|
| enabled | whether or not to enable capturing | 是否启用捕获。|

## Return Value 返回值

Returns 0 on success or -1 if not supported; call SDL_GetError() for more information.

如果成功则返回 0 ，不支持则返回 -1； 调用[SDL_GetError](http;//wiki.libsdl.org/SDL_GetError)()查看更多。

## Code Examples 示例代码

```c 
暂无
```


## Remarks 注意

Capturing enables your app to obtain mouse events globally, instead of just within your window. Not all video targets support this function. When capturing is enabled, the current window will get all mouse events, but unlike relative mode, no change is made to the cursor and it is not restrained to your window.

捕获你的应用程序在全局范围内鼠标的事件，而不只是你的窗口。不是所有的音频目标都支持这个功能。启用捕获时，在当前窗口获取所有鼠标事件，但不像相对模式，不会对光标进行任何更改和不会限制你的窗口。

This function may also deny mouse input to other windows--both those in your application and others on the system--so you should use this function sparingly, and in small bursts. For example, you might want to track the mouse while the user is dragging something, until the user releases a mouse button. It is not recommended that you capture the mouse for long periods of time, such as the entire time your app is running.

这个函数也可以拒绝鼠标输入到其他窗口，无论是在的你应用程序和系统上的其他窗口-----所以你应该谨慎的使用这个函数，并注意程序崩溃。举个例子，你可能想用户拖动某事时跟踪鼠标，直到用户释放鼠标按钮，不建议长时间捕获鼠标，例如你的应用程序运行的时的整个时间。

While captured, mouse events still report coordinates relative to the current (foreground) window, but those coordinates may be outside the bounds of the window (including negative values). Capturing is only allowed for the foreground window. If the window loses focus while capturing, the capture will be disabled automatically.

捕获时，鼠标事件仍然报告相对于当前窗口的坐标，但那些坐标可以在窗口的边界之外（包括负值）。仅允许捕获窗口的前景。如果捕获时窗口失去焦点，捕获将自动禁用。

While capturing is enabled, the current window will have the [SDL_WINDOW_MOUSE_CAPTURE](http://wiki.libsdl.org/SDL_WINDOW_MOUSE_CAPTURE)() flag set.

捕获启用时，当前窗口将具有设置[SDL_WINDOW_MOUSE_CAPTURE](http://wiki.libsdl.org/SDL_WINDOW_MOUSE_CAPTURE)() 的属性。

## Version 版本

This function is available since SDL 2.0.4.
这个函数可以用于 SDL 2.0.4

## Related Functions 相关函数

[SDL_GetGlobalMouseState](http：//wiki.libsdl.org/SDL_GetGlobalMouseState)

----------------------------------------------------------------------------
*[SixerME](https://github.com/DXkite) Translated*

