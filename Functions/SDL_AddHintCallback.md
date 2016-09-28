# [SDL_AddHintCallback](http://wiki.libsdl.org/SDL_AddHintCallback?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)

## Use this function to add a function to watch a particular hint.
使用这个函数来查看添加的函数是否有特定返回值。

## Syntax 语法 
```c
void SDL_AddHintCallback(const char* name,
                        SDL_AddHintCallback callback,
                        void*               userdata)
```

## Function Parameters 函数参数
|   参数   |  参数说明(EN)| 参数说明（ZH）
|----------|----------|-------------------------------------|
| callback | the function to call when the hint value change| 如果当前值变化就会调用这个函数|
| userdata | a pointer to pass to the callback function | 指针传递给回调函数|

## Code Examples 示例代码
```c
暂无
```

## Remarks 备注

The function prototype for callback is:
回调函数的类型：
```c
void SDL_AddHintCallback(void*          userdata,
                        const char* name,
                        const char* oldValue,
                        const char* newValue)
```
where its parameters are:
其中，它的参数是：
|userdata|what was passed as userdata to SDL_AddHintCallback   | 把用户数据传值到 SDL_AddHintCallback()  
|--------|--------|--------| 
| name   |what was passed as name to SDL_AddHintCallback()| 把名字传值到SDL_AddHintCallback()|
|oldValue|the old value | 原 值|
|newValue|the new value | 新 值|

## Version 版本
This function is available since SDL 2.0.0.
这个函数出自SDL 2.0.0.

## Related Function 相关函数
[SDL_DelhintCallback](http://wiki.libsdl.org/SDL_DelHintCallback)

--------------------------------------------------------------------------------------------------------
*@[SixerMe](https://github.com/DXkite) Translated.*