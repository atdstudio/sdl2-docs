# [SDL_AudioInit](http://wiki.libsdl.org/SDL_AudioInit?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)

Use this function to initialize a particular audio driver.

使用这个函数来初始化一个特定的音频驱动程式。

## Syntax 语法

```c 
int SDL_AudioInit(const char* driver_name)
```

## Function Parameters 函数参数

| 驱动名 | 解释(EN) | 解释(ZH) |
|------|---------|----------|
| driver_name | the name of the desired audio driver.| 音频驱动程式的名称。|


## Return Value 返回值

Returns 0 on success or a negative error code on failure; call SDL_GetError() for more information.

如果成功则返回值为0，否则返回为负的错误代码。调用 [SDL_GetError](http://wiki.libsdl.org/SDL_GetError)() 查看更多。

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

This function is used internally, and should not be used unless you have a specific need to designate the audio driver you want to use.
 You should normally use SDL_Init() or SDL_InitSubSystem().

这个函数是内部使用，除非你有一个具体指定的音频驱动程式，否则你不应该是使用。通常你需要使用 [SDL_Init](http://wiki.libsdl.org/SDL_Init)() 或者 [SDL_InitSubSystem](http://wiki.libsdl.org/SDL_InitSubSystem)().


## Related Functions 相关函数

[SDL_AudioQuit](http://wiki.libsdl.org/SDL_AudioQuit)

-----------------------------------------------------------------------
*[SixerMe](https://github.com/DXkite) Translated*

