# SDL_UpdateTexture
Use this function to update the given texture rectangle with new pixel data.   
使用该函数，使用新的像素数据为给定的纹理的一部分更新。
## Syntax 语法
```C
int SDL_UpdateTexture(SDL_Texture*    texture,
                      const SDL_Rect* rect,
                      const void*     pixels,
                      int             pitch)
```
## Function Parameters 函数参数

<table>
<tr><td><b>texture</b></td><td>the texture to update</td><td>要更新的纹理</td></tr>
<tr><td><b>rect</b></td><td>	
an <a href = "./../Structures/SDL_Rect.md">SDL_Rect</a> structure representing the area to update, or NULL to update the entire texture</td><td>代表要更新区域的<a href = "./../Structures/SDL_Rect.md">SDL_Rect</a>结构，或为NULL以代表更新整个纹理</td></tr>
<tr><td><b>pixels</b></td><td>the raw pixel data</td><td>像素数据</td></tr>
<tr><td><b>pitch</b></td><td>the number of bytes in a row of pixel data, including padding between lines</td><td>像素数据中一行像素的字节数，包括每一行的padding(为使数据对齐填充的空数据 译注)</td></tr>
</table>

## Return Value 返回值
Returns 0 on success or a negative error code on failure; call [SDL_GetError()](./SDL_GetError.md) for more information.   
执行成功返回0，若失败则返回一个负的错误码。调用[SDL_GetError()](./SDL_GetError.md)以获取更多的错误信息。
## Code Examples 代码示例
```C
暂无
```
## Remarks 注意
This is a fairly slow function, intended for use with static textures that do not change often.   
这是一个相当缓慢的函数，是为了不经常变化的静态(static)纹理设计的。

If the texture is intended to be updated often, it is preferred to create the texture as streaming and use the locking functions referenced below. While this function will work with streaming textures, for optimization reasons you may not get the pixels back if you lock the texture afterward.   
如果纹理可能会经常更新，你应该创造流式(streaming)的纹理并使用下方锁定函数。对于流式纹理(streaming textures)来说，虽然该函数也使纹理更新,但为了优化的原因，就算你之后锁定了纹理，使用该函数也得不到像素数据。(draft)
## Related Functions 相关函数
[SDL_CreateTexture](./SDL_CreateTexture.md)   
[SDL_LockTexture](./SDL_LockTexture.md)   
[SDL_UnlockTexture](./SDL_UnlockTexture.md)   

---
Translated by [SteDeshain](https://github.com/SteDeshain)   
Referenct to http://wiki.libsdl.org/SDL_UpdateTexture