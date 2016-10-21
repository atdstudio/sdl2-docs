# SDL_UnlockTexture
Use this function to unlock a texture, uploading the changes to video memory, if needed.   
使用该函数可以解除锁定一个纹理。如果需要，会把改变上传至显存中。
## Syntax 语法
```C
void SDL_UnlockTexture(SDL_Texture* texture)
```
## Function Parameters 函数参数

<table>
<tr><td><b>texture</b></td><td>a texture locked by <a href = "./SDL_LockTexture.md">SDL_LockTexture()</a></td><td>被<a href = "./SDL_LockTexture.md">SDL_LockTexture()</a>函数锁定过的纹理</td></tr>
</table>

## Code Examples 代码示例
```C
暂无
```
## Remarks 注意
![alert](./alert.png)WARNING: See [SDL bug #1586](http://bugzilla.libsdl.org/show_bug.cgi?id=1586) before using this function!   
![alert](./alert.png)警告：在使用该函数前应参考[SDL bug #1586](http://bugzilla.libsdl.org/show_bug.cgi?id=1586)
## Related Functions 相关函数
[SDL_LockTexture](./SDL_LockTexture.md)

---
Translated by [SteDeshain](https://github.com/SteDeshain)   
Reference to http://wiki.libsdl.org/SDL_UnlockTexture