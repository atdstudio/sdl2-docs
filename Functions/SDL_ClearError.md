# SDL_ClearError

Use this function to clear any previous error message.
使用本函数可以清除之前的错误信息。

## Syntax 函数声明
```c
void SDL_ClearError(void)
```
## Code Examples 使用示例
```c
const char *error = SDL_GetError();
if (*error) {
  SDL_Log("SDL error: %s", error);
  SDL_ClearError();
}
```

## Remarks 注意事项
> You can add useful comments here

## Related Functions 相关函数

[SDL_GetError](../Functions/SDL_GetError.md)	
[SDL_SetError](../Functions/SDL_SetError.md)	

-------------------------------------------------------------------
*@[DXkite](https://github.com/DXkite) Translated.*
