# [SDL_AudioQuit](http://wiki.libsdl.org/SDL_AudioQuit?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)

Use this function to shut down audio if you initialized it with SDL_AudioInit().

如果你使用这个函数初始化 [SDL_AudioInit](http://wiki.libsdl.org/SDL_AudioInit?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)() 
,则可以关闭声音。

## Syntax 语法

```c 
void SDL_AudioQuit(void)
```

## Code Examples 示例代码

```c 
int i;

for (i = 0; i < SDL_GetNumAudioDrivers(); ++i) {
    const char* driver_name = SDL_GetAudioDriver(i);
    if (SDL_AudioInit(driver_name)) {
        printf("Audio driver failed to initialize: %s\n", driver_name);
        continue;
    }
    SDL_AudioQuit();
}
```

## Remarks 备注

This function is used internally, and should not be used unless you have a specific need to specify the audio driver you want to use.
You should normally use SDL_Quit() or SDL_QuitSubSystem().

这个函数是内部使用，除非你有具体指定的声音驱动程式，否则，你不应该使用它。通常使用的函数是[SDL_Quit](http://wiki.libsdl.org/SDL_Quit)() 或者 [SDL_QuitSubSystem](http://wiki.libsdl.org/SDL_QuitSubSystem)().


## Related Functions 相关函数

[SDL_AudioInit](http://wiki.libsdl.org/SDL_AudioInit)()

------------------------------------------------------------------------------
*[SixerMe](https://github.com/DXkite) Translated*
