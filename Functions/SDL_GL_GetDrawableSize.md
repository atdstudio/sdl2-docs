# SDL_GL_GetDrawableSize

使用此函数获得窗口的可绘制大小（单位：像素）（用于glViewport）。
```c
void SDL_GL_GetDrawableSize(SDL_Window* window,
                            int*        w,
                            int*        h)
```

## 参数
| 参数 | 说明 |
|------|-----|
|window	|要获取Drawable大小的窗口|
|w	|指向int的指针，它会被设置为Drawable宽度|
|h|	指向int的指针，它会被设置为Drawable高度|

## Remarks
如果我们在渲染一个高DPI的Drawable，这可能和SDL_GetWindowSize是不同的，如果窗口在创建时指定了SDL_WINDOW_ALLOW_HIGHDPI支持（被苹果称为“Retina”），这将不会被SDL_HINT_VIDEO_HIGHDPI_DISABLE hint所禁用。

