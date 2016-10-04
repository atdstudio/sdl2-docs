# [SDL_AndroidGetInternalStoragePath](http://wiki.libsdl.org/SDL_AndroidGetInternalStoragePath?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)

User this function to get the path used for internal storage for this application.
使用这个函数可以使应用程序。

## Syntax 语法
```c 
const char* SDL_AndroidGetInternalStoragePath()
```

## Return Value 返回值

Return the path used for internal storage for this application on success or NULL on failure; call SDL_GetError()() for more infromation.
应用程序返回成功的值是内部存储的路径，失败则是NULL； 调用[SDL_GetError](http://wiki.libsdl.org/SDL_GetError)()查看更多信息。

## Code Examples 代码示例
```c 
暂无
```

## Remarks 注意

This path is unique to your application and cannot be written to by other application.

这是应用程序唯一的路径,但是其他的应用程序不可以使用。

Your internal storage path is typically: /data/data/your.app.package/files.
一般的内部存储路径是： /data/data/your.app.package/files.

## Version 版本

This function is available since SDL 2.0.0.
这个函数出自 SDL 2.0.0

## Related Function 相关函数
[SDL_AndroidGetExternalStorageState](http://wiki.libsdl.org/SDL_AndroidGetExternalStorageState)

----------------------------------------------------------------------------------\
*@[SixerMe](https://github.com/DXkite)  Translated.*
