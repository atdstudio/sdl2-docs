# [SDL_AndroidGetExternalStorageState](http://wiki.libsdl.org/SDL_AndroidGetExternalStorageState?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)

Use this function to get the current state of external storage.
使用这个函数可以获取当前的外部存储状态。

## Syntax　语法
```c 
int SDL_AndroidGetExternalStorageState()
```

## Return Value 返回值

Returns the current state of external storage on success or 0 on failure; call SDL_GetError() for more information.
如果返回当前的外部存储状态则为成功，返回数值0则为失败；调用[SDL_GetError](http://wiki.libsdl.org/SDL_GetError)()查看更多信息。

## Code Examples 代码示例
```c 
暂无
```

## Remarks 注意

The current state of external storage, a bitmask of these values: SDL_ANDROID_EXTERNAL_STORAGE_READ, SDL_ANDROID_EXTERNAL_STORAGE_WRITE.
当前外部路径的状态，它的值应该是位掩码：SDL_ANDROID_EXTERNAL_STORAGE_READ, SDL_ANDROID_EXTERNAL_STORAGE_WRITE.
If external storage is currently unavailable, this will return 0.
如果当前的外部存储不可用，那么返回的值将是数值0.

## Version 版本

This function is available since SDL 2.0.0.
此函数出自 SDL 2.0.0

## Related Functions 相关函数

[SDL_AndroidGetExternalStoragePath](http://wiki.libsdl.org/SDL_AndroidGetExternalStoragePath).

----------------------------------------------------------------------------------------
*@[SixerMe](https://github.com/DXkite) Translated*

