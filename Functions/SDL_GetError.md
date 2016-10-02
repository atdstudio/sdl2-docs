#[SDL_GetError](https://wiki.libsdl.org/SDL_GetError)
Use this function to retrieve a message about the last error that occurred.  
使用该函数检索最后一次出错的信息。

##Syntax 语法
```C
const char* SDL_GetError()
```
##Return Value 返回值
Returns a message with information about the specific error that occurred, or an empty string if there hasn't been an error message set since the last call to [SDL_ClearError](SDL_ClearError.md)(). The message is only applicable when an SDL function has signaled an error. You must check the return values of SDL function calls to determine when to appropriately call [SDL_GetError](SDL_GetError.md)().  
返回一个出错的消息，如果当前从上一次调用 [SDL_ClearError](SDL_ClearError.md)() 后没有错误发生则返回空字符串。注意该函数只会在发生错误时才有效，你必须通过检查函数的返回值来决定什么时候应该调用 [SDL_GetError](SDL_GetError.md)().

##Code Examples 代码示例
```C
if (SDL_Init(SDL_INIT_EVERYTHING) < 0) {
    // 发生错误
    printf("SDL_Init failed: %s\n", SDL_GetError());
}
```
Note: Although this example uses [SDL_Init](SDL_Init.md)(), [SDL_GetError](SDL_GetError.md)() provides an error message for any failed SDL operation which supports error reporting, see the wiki page for each particular SDL function.  
注意：虽然这个例子使用的是 [SDL_Init](SDL_Init.md)(), 但是该函数对任何支持返回错误代码的函数都有效，请到各个函数对应的页面查看说明。

##Remarks 注释
It is possible for multiple errors to occur before calling [SDL_GetError](SDL_GetError.md)(). Only the last error is returned.  
程序中可能会产生多个错误。但该函数只返回最后一次的错误信息。

The returned string is statically allocated and must not be freed by the application.  
该函数返回字符串的内存是静态分配的，不能由程序释放。

##Related Functions 相关函数
[SDL_ClearError](SDL_ClearError.md)  
[SDL_SetError](SDL_SetError.md)

---
*@[lxfly2000](https://github.com/lxfly2000)*
