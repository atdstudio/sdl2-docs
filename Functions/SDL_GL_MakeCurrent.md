# SDL_GL_MakeCurrent

使用此函数设置一个用于渲染到该OpenGL窗口的OpenGL上下文。

```c
int SDL_GL_MakeCurrent(SDL_Window*   window,
                       SDL_GLContext context)
```

## 参数
window	用于设置当前上下文的窗口
context	OpenGL上下文

## 返回值
返回0则成功，返回负数则失败，调用SDL_GetError()获得更多消息。


---
by  @[星翼](https://git.oschina.net/Luma) `ACGCross游戏开发组成员`