#[SDL_RenderCopyEx](https://wiki.libsdl.org/SDL_RenderCopyEx)
Use this function to copy a portion of the texture to the current rendering target, optionally rotating it by angle around the given center and also flipping it top-bottom and/or left-right.  
使用该函数复制材质图像的一部分至当前的渲染目标，可以按一定的角度按指定旋转中心旋转或上下/左右翻转。

##Syntax 语法
```C
int SDL_RenderCopyEx(SDL_Renderer*          renderer,
                     SDL_Texture*           texture,
                     const SDL_Rect*        srcrect,
                     const SDL_Rect*        dstrect,
                     const double           angle,
                     const SDL_Point*       center,
                     const SDL_RendererFlip flip)
```
##Function Parameters 函数参数
<table>
<tr><td><b>renderer</b></td><td>the rendering context<br/>渲染器</td></tr>
<tr><td><b>texture</b></td><td>the source texture; see <a href="#remarks-注释">Remarks</a> for details<br/>源材质，详细请看<a href="#remarks-注释">注释</a>。</td></tr>
<tr><td><b>srcrect</b></td><td>the source <a href="../Structures/SDL_Rect.md">SDL_Rect</a> structure or NULL for the entire texture<br/><a href="../Structures/SDL_Rect.md">SDL_Rect</a> 结构体指定的要复制的源材质的矩形区域或者 NULL 为整个材质图像。</td></tr>
<tr><td><b>dstrect</b></td><td>the destination <a href="../Structures/SDL_Rect.md">SDL_Rect</a> structure or NULL for the entire rendering target<br/><a href="../Structures/SDL_Rect.md">SDL_Rect</a> 结构体指定的目标矩形区域或者 NULL 为渲染器的整个区域。</td></tr>
<tr><td><b>angle</b></td><td>an angle in degrees that indicates the rotation that will be applied to dstrect<br/>旋转角度（角度制）</td></tr>
<tr><td><b>center</b></td><td>a pointer to a point indicating the point around which dstrect will be rotated (if NULL, rotation will be done around dstrect.w/2, dstrect.h/2)<br/>旋转中心，如果指定 NULL 则为材质图像的中心。</td></tr>
<tr><td><b>flip</b></td><td>a <a href="../Enumerations/SDL_RendererFlip.md">SDL_RendererFlip</a> value stating which flipping actions should be performed on the texture<br/>指定翻转参数。</td></tr>
</table>
##Return Value 返回值
Returns 0 on success or a negative error code on failure; call [SDL_GetError](SDL_GetError.md)() for more information.  
成功返回 0, 否则返回一个负数的错误码；调用 [SDL_GetError](SDL_GetError.md)() 获取更多信息。

##Code Examples 代码示例
```
暂无。
```
##Remarks 注释
The texture is blended with the destination based on its blend mode set with [SDL_SetTextureBlendMode](SDL_SetTextureBlendMode.md)().  
渲染后的材质根据 [SDL_SetTextureBlendMode](SDL_SetTextureBlendMode.md)() 的设置会带有混合效果。

The texture color is affected based on its color modulation set by [SDL_SetTextureColorMod](SDL_SetTextureColorMod.md)().  
材质的颜色是受 [SDL_SetTextureColorMod](SDL_SetTextureColorMod.md)() 影响的。

The texture alpha is affected based on its alpha modulation set by [SDL_SetTextureAlphaMod](SDL_SetTextureAlphaMod.md)().  
材质的透明度是受 [SDL_SetTextureAlphaMod](SDL_SetTextureAlphaMod.md)() 影响的。

##Related Functions 相关函数
[SDL_RenderCopy](SDL_RenderCopy.md)  
[SDL_SetTextureAlphaMod](SDL_SetTextureAlphaMod.md)  
[SDL_SetTextureBlendMode](SDL_SetTextureBlendMode.md)  
[SDL_SetTextureColorMod](SDL_SetTextureColorMod.md)

---
*@[lxfly2000](https://github.com/lxfly2000)*
