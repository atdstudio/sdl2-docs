# SDL_GL_LoadLibrary

使用此函数动态加载OpenGL实现库。

```c
int SDL_GL_LoadLibrary(const char* path)
```

## 参数：
path	平台相关的OpenGL实现库名称，传入NULL则使用默认的OpenGL实现库。

## 返回值：
返回0则成功，返回负值则失败，调用SDL_GetError()获得更多消息。

## Remarks
这应该在初始化视频驱动后执行，但是要在创建任何OpenGL窗口之前，如果没有OpenGL实现库被加载，那么默认的库就会被加载并创建第一个OpenGL窗口。
你完成动态加载后，你需要使用SDL_GL_GetProcAddress()来获取OpenGL的函数。

译注：如果不调用此函数直接创建OpenGL窗口，那么在SDL2.0.4里可能不会得到任何扩展的支持，也无法使用高阶OpenGL函数。


---
by  @[星翼](https://git.oschina.net/Luma) `ACGCross游戏开发组成员`
