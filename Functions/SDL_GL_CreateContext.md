# SDL_GL_CreateContext

使用此函数为OpenGL窗口创建一个OpenGL上下文，并且设置为当前上下文。
```c
SDL_GLContext SDL_GL_CreateContext(SDL_Window* window)
```
## Function Parameters 函数相关参数
| 参数名 |解释 |
|--------|-----|
| window|要被创建上下文的窗口|



##  返回值
返回传入的窗口的OpenGL上下文，如果发生错误则返回NULL，可以使用SDL_GetError()获得更多建议。

## 示例
```c
// 窗口必须有SDL_WINDOW_OPENGL标志才可以创建OpenGL上下文
SDL_Window *window = SDL_CreateWindow(
    "SDL2/OpenGL Demo", 0, 0, 640, 480, 
    SDL_WINDOW_OPENGL|SDL_WINDOW_RESIZABLE);
  
//  创建OpenGL上下文
SDL_GLContext glcontext = SDL_GL_CreateContext(window);

// 现在可以使用OpenGL函数
glClearColor(0,0,0,1);
glClear(GL_COLOR_BUFFER_BIT);
SDL_GL_SwapWindow(window);

// 一旦完成OpenGL函数，你就可以删除OpenGL上下文
SDL_GL_DeleteContext(glcontext);  
```


## Remarks

Windows用户使用高阶OpenGL时应该注意，由于历史原因，GL函数默认仅仅支持到OpenGL 1.1.高阶函数必须在运行时加载，同时可以使用SDL_GL_GetProcAddress()函数获取这些扩展中的函数。

---
by  @[星翼](https://git.oschina.net/Luma) `ACGCross游戏开发组成员`