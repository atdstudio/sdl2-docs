#[SDL_BlendMode](https://wiki.libsdl.org/SDL_BlendMode)
An enumeration of blend modes used in [SDL_RenderCopy](../Functions/SDL_RenderCopy.md)() and drawing operations.

在 [SDL_RenderCopy](../Functions/SDL_RenderCopy.md)() 中和绘图操作用到的混合模式的枚举值。

##Values 值
<table>
<tr><td>SDL_BLENDMODE_NONE</td><td>no blending 不使用混合<br/>dstRGBA = srcRGBA</td></tr>
<tr><td>SDL_BLENDMODE_BLEND</td><td>alpha blending 透明<br/>dstRGB = (srcRGB * srcA) + (dstRGB * (1-srcA))<br/>dstA = srcA + (dstA * (1-srcA))</td></tr>
<tr><td>SDL_BLENDMODE_ADD</td><td>additive blending 加法混合<br/>dstRGB = (srcRGB * srcA) + dstRGB<br/>dstA = dstA</td></tr>
<tr><td>SDL_BLENDMODE_MOD</td><td>color modulate 颜色调制<br/>dstRGB = srcRGB * dstRGB<br/>dstA = dstA</td></tr>
</table>
##Code Examples 代码示例
```
暂无
```
##Remarks 注释
**暂无**
##Related Structures 相关结构体
[SDL_RenderInfo](../Structures/SDL_RendererInfo.md)
##Related Functions 相关函数
[SDL_GetRenderDrawBlendMode](../Functions/SDL_GetRenderDrawBlendMode.md)

[SDL_GetSurfaceBlendMode](../Functions/SDL_GetSurfaceBlendMode.md)

[SDL_GetTextureBlendMode](../Functions/SDL_GetTextureBlendMode.md)

[SDL_RenderCopy](../Functions/SDL_RenderCopy.md)

[SDL_SetRenderDrawBlendMode](../Functions/SDL_SetRenderDrawBlendMode.md)

[SDL_SetSurfaceBlendMode](../Functions/SDL_SetSurfaceBlendMode.md)

[SDL_SetTextureBlendMode](../Functions/SDL_SetTextureBlendMode.md)

---
*@[lxfly2000](https://github.com/lxfly2000)*
