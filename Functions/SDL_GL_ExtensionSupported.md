# SDL_GL_ExtensionSupported

使用此函数检查当前上下文是否支持要求的OpenGL扩展。

```c 
SDL_bool SDL_GL_ExtensionSupported(const char* extension)
```


## 参数
extension 要检查的扩展名称

## 返回值
如果支持，那么返回SDL_TRUE，否则返回SDL_FALSE。

## 代码示例
```c
if (SDL_GL_ExtensionSupported("GL_EXT_framebuffer_blit")) {
        draw_to_the_screen_with_framebuffer_blit();   // 更快！
    } else {
        draw_to_the_screen_with_a_textured_quad();  // 更慢！
    }
```

## Remarks

这个函数将会在当前GL上下文进行操作，你必须在调用此函数前创建一个上下文，不要假设你所有的上下文都拥有相同的扩展，重新创建一个已有的上下文将提供相同的扩展。
虽然它可能没有太大的开销，但是这个函数不是O(1)操作。你需要检查你关心的扩展并保存在起来而不是每次都检查是否拥有此扩展。

---
by  @[星翼](https://git.oschina.net/Luma) `ACGCross游戏开发组成员`