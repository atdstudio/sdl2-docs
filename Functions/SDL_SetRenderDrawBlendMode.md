#[SDL_SetRenderDrawBlendMode](https://wiki.libsdl.org/SDL_SetRenderDrawBlendMode)
Use this function to set the blend mode used for drawing operations (Fill and Line).  
使用该函数设置绘图操作的混合模式（填充，线条）

##Syntax 语法
```C
int SDL_SetRenderDrawBlendMode(SDL_Renderer* renderer, SDL_BlendMode blendMode)
```
##Function Parameters 函数参数
<table>
<tr><td><b>renderer</b></td><td>the rendering context<br/>渲染器</td></tr>
<tr><td><b>blendMode</b></td><td>the <a href="../Enumerations/SDL_BlendMode.md">SDL_BlendMode</a> to use for blending; see <a href="#remarks-注释">Remarks</a> for details<br/>表示混合模式的 <a href="../Enumerations/SDL_BlendMode.md">SDL_BlendMode</a> 枚举值；详细请看<a href="#remarks-注释">注释</a>。</td></tr>
</table>
##Return Value 返回值
Returns 0 on success or a negative error code on failure; call [SDL_GetError](SDL_GetError.md)() for more information.  
成功返回 0, 否则返回一个负数的错误码；调用 [SDL_GetError](SDL_GetError.md)() 获取更多信息。
##Code Examples 代码示例
```
暂无。
```
##Remarks 注释
**blendMode** may be one of the following:  
**blendMode** 可以是下列任一值：
<table>
<tr><td>SDL_BLENDMODE_NONE</td><td>no blending 不使用混合<br/>dstRGBA = srcRGBA</td></tr>
<tr><td>SDL_BLENDMODE_BLEND</td><td>alpha blending 透明<br/>dstRGB = (srcRGB * srcA) + (dstRGB * (1-srcA))<br/>dstA = srcA + (dstA * (1-srcA))</td></tr>
<tr><td>SDL_BLENDMODE_ADD</td><td>additive blending 加法混合<br/>dstRGB = (srcRGB * srcA) + dstRGB<br/>dstA = dstA</td></tr>
<tr><td>SDL_BLENDMODE_MOD</td><td>color modulate 颜色调制<br/>dstRGB = srcRGB * dstRGB<br/>dstA = dstA</td></tr>
</table>
##Related Functions 相关函数
[SDL_GetRenderDrawBlendMode](SDL_GetRenderDrawBlendMode.md)  
[SDL_RenderDrawLine](SDL_RenderDrawLine.md)  
[SDL_RenderDrawLines](SDL_RenderDrawLines.md)  
[SDL_RenderDrawPoint](SDL_RenderDrawPoint.md)  
[SDL_RenderDrawPoints](SDL_RenderDrawPoints.md)  
[SDL_RenderDrawRect](SDL_RenderDrawRect.md)  
[SDL_RenderDrawRects](SDL_RenderDrawRects.md)  
[SDL_RenderFillRect](SDL_RenderFillRect.md)  
[SDL_RenderFillRects](SDL_RenderFillRects.md)

---
*@[lxfly2000](https://github.com/lxfly2000)*
