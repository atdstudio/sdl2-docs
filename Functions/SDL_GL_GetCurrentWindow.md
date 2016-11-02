# SDL_GL_GetCurrentWindow

使用此函数获取当前激活的OpenGL窗口。
```c
SDL_Window* SDL_GL_GetCurrentWindow(void)
```

## 返回值
返回当前的激活的OpenGL窗口，失败则会返回NULL，调用SDL_GetError()获取更多信息。

---
by  @[星翼](https://git.oschina.net/Luma) `ACGCross游戏开发组成员`