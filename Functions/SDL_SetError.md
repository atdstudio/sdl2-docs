# SDL_SetError

Use this function to set the SDL error message.
使用函数可以设置一个SDL错误信息。

## Syntax 函数声明
```c
int SDL_SetError(const char* fmt,
                 ...)
```
## Function Parameters 函数参数

<table>
<tr><th>fmt</th><td>a printf() style message format string 像printf函数一样的字符串</td></tr>
<tr><th>...</th><td> additional parameters matching % tokens in the fmt string, if any <br> 函数的格式化输出的参数列表</td></tr>
</table>

## Return Value 返回值

Returns always -1.
总是返回 -1

## Code Examples
```c
SDL_SetError("Something unexpected happened!");

int errorCode = 0;
...
errorCode = -37;
...
if (errorCode < 0)
    SDL_SetError("Something unexpected happened: Error Code %d", errorCode);
```

## Remarks  注意

Calling this function will replace any previous error message that was set.
这个函数会覆盖之前设置的错误。

## Related Functions 相关函数

[SDL_ClearError](../Functions/SDL_ClearError.md)	

[SDL_GetError](../Functions/SDL_GetError.md)	

-------------------------------------------------------------------
*@[DXkite](https://github.com/DXkite) Translated.*