# SDL_GetTextureAlphaMod
Use this function to get the additional alpha value multiplied into render copy operations.   
使用该函数可以得到纹理附加的alpha值，在执行渲染拷贝操作时会乘以该alpha值。
## Syntax 语法
```C
int SDL_GetTextureAlphaMod(SDL_Texture* texture,
                           Uint8*       alpha)
```
## Function Parameters 函数参数

<table>
<tr><td><b>texture</b></td><td>the texture to query</td><td>要查询的纹理</td></tr>
<tr><td><b>alpha</b></td><td>a pointer filled in with the current alpha value</td><td>用来储存当前alpha值的变量的指针</td></tr>
</table>

## Return Value 返回值
Returns 0 on success or a negative error code on failure; call [SDL_GetError()](./SDL_GetError.md) for more information.   
执行成功返回0，若失败则返回一个负的错误码。调用[SDL_GetError()](./SDL_GetError.md)以查看更多错误信息。
## Code Examples 代码示例
```C
暂无
```
## Remarks 注意
暂无
## Related Functions 相关函数
[SDL_GetTextureColorMod](./SDL_GetTextureColorMod.md)   
[SDL_SetTextureAlphaMod](./SDL_SetTextureAlphaMod.md)

---
Translated by [SteDeshain](https://github.com/SteDeshain)   
Reference to http://wiki.libsdl.org/SDL_GetTextureAlphaMod