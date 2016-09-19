Translate By DXkite Reference: http://wiki.libsdl.org/SDL_AddEventWatch?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29

# [SDL_AddEventWatch](http://wiki.libsdl.org/SDL_AddEventWatch?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)

在事件添加到事件队列时添加一个回调函数。

## 语法

```c
void SDL_AddEventWatch(SDL_EventFilter filter,
                       void*           userdata) 
```

## 函数参数
|参数|说明|
|----|----|
| filter |当一个事件发生时调用的过滤函数，查看‘注意’了解跟多信息。  |
| userdata | 一个传递给过滤函数的指针|

## 注意
过滤函数的原型是：

```c
int YourEventFilter(void*      userdata,
                    SDL_Event* event)
```
`YourEventFilter`是你过滤函数的名字，它的参数为：
|参数|说明|
|---|----|
|userdata|在调用函数`SDL_AddEventWatch`()时设置的数据指针 |
|event|触发回调的事件|

过滤函数会在事件发生时被调用，但是函数的返回值会被忽略。  
**警告: 在过滤函数中做的任何事情都要小心, 该函数可能会在其他线程被调用**    
如果退出事件是由一个信号产生的（例如SIGINT），它将绕过内部队列，直接交付给回调函数，并立即到达下一个事件的监听（`event poll`)。   
注意: 回调函数调用是通过用户通过[SDL_PushEvent](./SDL_PushEvent.md)()发布的事件调用时调用，而不是为 未开启的事件、通过[SDL_SetEventFilter](SDL_SetEventFilter.md)()设置的事件过滤、
用户通过函数[SDL_PeepEvents](SDL_PeepEvents.md)()触发的事件调用。

## 相关函数
[SDL_DelEventWatch](SDL_DelEventWatch.md)    
[SDL_SetEventFilter](SDL_SetEventFilter.md)