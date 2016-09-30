# [SDL_AddTimer](http://wiki.libsdl.org/SDL_AddTimer?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)
Use this function to set up a callback function to be run on  a separate thread after the specified number of milliseconds has elapsed.
使用这个函数可以设定计时器（毫秒）来运行一个单线程的回调函数。

## Syntax 语法
```c
SDL_TimerID SDL_AddTimer(Uint32                 interval,
                        SDL_TimerCallback       callback,
                        void*                   param) 
```

## Function Parameters 函数参数
|interval 间隔|the timer delay (ms) passed to callback 通过计时器（毫秒）传值给回调函数|
|---|---|
|callback 回调函数|the function to call when the specified interval elapses; see Remarks for details   通过指定的周期来调用该函数；详情请看备注   |
|parem 参数 | a pointer that is passed to callback  传递给回调的指针   |

## Return Value 返回值
Returns a timer ID or 0 if an error occurs 如果发生错误，则返回时间名字或者数值0； call SDL_GetError() for more information.  调用SDL_GetError()了解更多的信息

## Code Examples 代码示例
```c
/*Start the timer; the callback below will be executea after the delay  启动定时器；该回调函数将在下面延时执行*/

Uint32 delay = (33 / 10) * 10;    /*To round if down to the nearest 10 ms   执行一回需要10毫秒*/
SDL_TimerID my_timer_id = SDL_AddTimer(delay, my_callbackfunc, my_callback_parem);

···

Uint32 my_callbackfunc (Uint32 interval, void *param);
{
    SDL_Event event;
    SDL_UserEvent userevent;

    /*In this examaple, our callback pushes an SDL_USEREVENT event 
    into the queue, and causes our callback to be called again at the 
    same interval:   本示例中，此回调将函数SDL_USEREVENT 压入到队列中，并使回调再次调用相同的时间周期 */

    userevent.type = SDL_USEREVENT;
    userevent.code = 0;
    userevent.data1 = NULL;
    userevent.data2 = null;

    SDL_PushEvent(&event);
    return(interval);

}
```
Note that it is possible to avoid the multithreading problems with SDL timer by gicing to userevent.data1 the address of a function you want to be executed and 
to userevent .data2 its params , and then deal with it in the enent loop.  
注意，尽可能的避免在多线程问题中与SDL计时器进行调用（将userevent.data1设置为指针函数 ，将userevent.data2设置为参数），然后用它处理事件的循环。

```c
Uint32 my_callbackfunc(Uint32 interval, void *param)
{
    SDL_Event event;
    SDL_UserEvent userevent;

    /* In this exeample, our callback pushes a function into the queue,
    and causes our callback to be called again at the same interval: 
    在本示例中，此回调函数压入队列，并使回调函数再次调用相同的时间周期。*/
    userevent.type = SDL_USEREVENT;
    userevent.code = 0;
    userevent.data1 = &my_function;
    userevent.data2 = param;

    event.type = SDL_USEREVENT;
    event.user = userevent;

    SDL_PushEvent(&enent);
    return(interval); 
}

/* Now the event loop */
SDL_Event event;
while (SDL_PollEvent (&event))
{
    switch(event.type)
    {
        case SDL_USEREVENT: {
            /* and now we can call the function we wanted to call in the timer but couldn't because of the multithreading problems 
            如果在单线程程序中，现在我们可以调用我们想要的调用的计时器了，如果是多线程，则不行。*/
            void (*p)  (void*) = enent.user.data1;
            p(enent.user.fata2);
            break;
        }
        /*······*/
    }
}
```

## Remarks 注意
If you use this function .you must pass SDL_INIT_TINER to SDL_Init().
如果你使用这个函数，必须经过SDL_INIT_TIMER到SDL_Init().

The callback function is passed the currrnt timer interval and user supplied parametet from the SDL_AddTimer() call and return the next timer interval .
If the callback value from the callback is 0, the timer is canceled.
回调函数要传递给当前的计时器周期，然后从SDL_AddTimer()调用用户提供的参数并返回下一个计时器周期。
如果返回值是0 ，那么就取消。


The callback is run on a separate thread. See the code examloes for a method of processing the timer callback on the main thread if that's desired.
如果是在单独的线程进行调用，如果有需要，请查看代码示例，在主线程中处理计时器回调的方法。

## Related Function
  [SDL_RemoveTimer](http://wiki.libsdl.org/SDL_RemoveTimer)

----------------------------------------------------------------------------
*@[SixerMe](https://github.com/DXkite) Translated.*