# SDL_GL_SwapWindow

使用此函数更新窗口和OpenGL渲染器。

```c
void SDL_GL_SwapWindow(SDL_Window* window)
```
## 参数
window 要更新的OpenGL窗口。

## Remarks
默认使用双缓冲OpenGL上下文。
在Mac OS X上确保你在交换缓存前已经绑定0到帧缓存，否则什么都不会发生，看下面博客获得更多信息：
http://renderingpipeline.com/2012/05/nsopenglcontext-flushbuffer-might-not-do-what-you-think/

---
by  @[星翼](https://git.oschina.net/Luma) `ACGCross游戏开发组成员`

