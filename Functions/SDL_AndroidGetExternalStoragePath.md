
# [SDL_AndroidGetExternalStoragePath](http://wiki.libsdl.org/SDL_AndroidGetExternalStoragePath?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)

Use this function to get the path user for external storage for this application.
使用这个函数可以使应用程序获取外部存储路径。

## Syntax 语法
```c 
const char* SDL_AndroidGetExternalStoragePath()
```

## Return Value 返回值
如果是成功的返回值是应用程序的外部存储卡的路径，否则返回NULL则是失败；调用[SDL_GetError](http://wiki.libsdl.org/SDL_GetError)()查看更多信息。

## Code Examples 代码示例
```c 
暂无
```

## Remarks　注意
This path is unique to your application, but is public and can be written to by other application.
Your external storage path is typicall:/storage/sdcard0/Android/data/your.app.package/faies.
对于应用程序来说是唯一的路径，但是由于是外部存储设备，所以其他的应用程序也可以写入。
一般的外部存储路径都是/storage/sdcard0/Android/data/your.app.package/files.


## Version 版本

This function is available since SDL 2.0.0

该函数来自SDL 2.0.0

## Related Function 相关函数

[SDL_AndroidGetExternalStorageState](http://wiki.libsdl.org/SDL_AndroidGetExternalStorageState)

------------------------------------------------------------------------------------------------------
*@[SixerMe](https://github.com/DXkite) Translated.*