# SDL_LockTexture
Use this function to lock a portion of the texture for **write-only** pixel access.   
使用该函数可以锁定纹理的一部分，该部分像素**只有可写**的访问权限。
## Syntax 语法
```C
int SDL_LockTexture(SDL_Texture*    texture,
                    const SDL_Rect* rect,
                    void**          pixels,
                    int*            pitch)
```
## Function Parameters 函数参数

<table>
	<tr>
		<td><b>texture</b></td>
		<td>the texture to lock for access, which was created with SDL_TEXTUREACCESS_STREAMING</td>
		<td>为访问并要锁定的纹理，该纹理在创建时必须使用SDL_TEXTUREACCESS_STREAMING</td>
	</tr>
	<tr>
		<td><b>rect</b></td>
		<td>an <a href = "./../Structures/SDL_Rect.md">SDL_Rect</a> structure representing the area to lock for access; NULL to lock the entire texture</td>
		<td>代表要锁定访问的区域的<a href = "./../Structures/SDL_Rect.md">SDL_Rect</a>结构，或为NULL以代表锁定整个纹理。</td>
	</tr>
	<tr>
		<td><b>pixels</b></td>
		<td>this is filled in with a pointer to the locked pixels, appropriately offset by the locked area</td>
		<td>一个指针的地址，该指针指向锁定的像素，该区块的像素已根据锁定的区域做好了偏移处理。</td>
	</tr>
	<tr>
		<td><b>pitch</b></td>
		<td>this is filled in with the pitch of the locked pixels; the pitch is the length of one row in bytes</td>
		<td>一个变量的地址，该变量为锁定的像素的对齐长度。该值为每一行像素的字节长度。</td>
	</tr>
</table>

## Return Value 返回值
Returns 0 on success or a negative error code if the texture is not valid or was not created with SDL_TEXTUREACCESS_STREAMING; call [SDL_GetError()](./SDL_GetError.md) for more information.   
执行成功返回0，若纹理无效，或该纹理不是用SDL_TEXTUREACCESS_STREAMING创建的则返回一个负的错误码。调用[SDL_GetError()](./SDL_GetError.md)以获取更多的错误信息。
## Code Examples 代码示例
```C
暂无
```
## Remarks 注意
As an optimization, the pixels made available for editing don't necessarily contain the old texture data. This is a write-only operation, and if you need to keep a copy of the texture data you should do that at the application level.   
为了优化，获取访问用以编辑的像素并不需要包含旧的像素数据。这是一个只写的操作，而且如果你需要得到纹理数据的一份拷贝，你应该在应用层面做这一操作。

You must use [SDL_UnlockTexture()](./SDL_UnlockTexture.md) to unlock the pixels and apply any changes.   
你必须调用[SDL_UnlockTexture()](./SDL_UnlockTexture.md)来解除锁定并且应用任何改变。
## Related Functions 相关函数
[SDL_UnlockTexture](./SDL_UnlockTexture.md)

---
Translated by [SteDeshain](https://github.com/SteDeshain)   
Reference to http://wiki.libsdl.org/SDL_LockTexture