# SDL_GL_GetCurrentContext

使用此函数获取当前的OpenGL上下文。
```c 
SDL_GLContext SDL_GL_GetCurrentContext(void)
```
## 返回值
返回当前激活的OpenGL上下文，失败的时候将返回NULL，可以调用SDL_GetError()获取更多信息。
---
by  @[星翼](https://git.oschina.net/Luma) `ACGCross游戏开发组成员`

