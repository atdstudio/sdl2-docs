# SDL_RenderReadPixels
Use this function to read pixels from the current rendering target.   
使用该函数可以从当前渲染目标中读取像素数据。
## Syntax 语法
```C
int SDL_RenderReadPixels(SDL_Renderer*   renderer,
                         const SDL_Rect* rect,
                         Uint32          format,
                         void*           pixels,
                         int             pitch)
```
## Function Parameters 函数参数

<table>
<tr><td><b>renderer</b></td><td>the rendering context</td><td>渲染器</td></tr>
<tr><td><b>rect</b></td><td>an <a href = "./../Structures/SDL_Rect.md">SDL_Rect</a> structure representing the area to read, or NULL for the entire render target</td><td>代表要读取的矩形区域的<a href = "./../Structures/SDL_Rect.md">SDL_Rect</a>结构</td></tr>
<tr><td><b>format</b></td><td>the desired format of the pixel data, or 0 to use the format of the rendering target; see <a href = "#remarks-注意">Remarks</a> for details</td><td>像素数据所需求的格式，或者为0表示用渲染目标的格式。查看<a href = "#remarks-注意">注意</a>以获取详细信息</td></tr>
<tr><td><b>pixels</b></td><td>a pointer filled in with the pixel data</td><td>用来储存像素数据的指针</td></tr>
<tr><td><b>pitch</b></td><td>the pitch of the <b>pixels</b> parameter</td><td><b>pixels</b>参数的对齐值(pitch: 矩形中每一行像素的字节数，译注)</td></tr>
</table>

## Return Value 返回值
Returns 0 on success or a negative error code on failure; call [SDL_GetError()](./SDL_GetError.md) for more information.   
执行成功返回0，若失败则返回一个负的错误码。调用[SDL_GetError()](./SDL_GetError.md)以获取更多错误信息。
## Code Examples 代码示例
```C
暂无
```
## Remarks 注意
![alert](./alert.png)WARNING: This is a very slow operation, and should not be used frequently.   
警告：该操作很缓慢，不应该频繁使用。   
<b>format</b> may be one of the following:
参数<b>format</b>可以是以下值中的一个：

<table>
<tr><td>SDL_PIXELFORMAT_UNKNOWN</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_INDEX1LSB</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_INDEX1MSB</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_INDEX4LSB</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_INDEX4MSB</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_INDEX8</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_RGB332</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_RGB444</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_RGB555</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_BGR555</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_ARGB4444</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_RGBA4444</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_ABGR4444</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_BGRA4444</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_ARGB1555</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_RGBA5551</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_ABGR1555</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_BGRA5551</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_RGB565</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_BGR565</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_RGB24</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_BGR24</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_RGB888</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_RGBX8888</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_BGR888</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_BGRX8888</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_ARGB8888</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_RGBA8888</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_ABGR8888</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_BGRA8888</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_ARGB2101010</td><td></td></tr>
<tr><td>SDL_PIXELFORMAT_RGBA32</td><td>alias for RGBA byte array of color data, for the current platform (>= SDL 2.0.5)</td></tr>
<tr><td>SDL_PIXELFORMAT_ARGB32</td><td>alias for ARGB byte array of color data, for the current platform (>= SDL 2.0.5)</td></tr>
<tr><td>SDL_PIXELFORMAT_BGRA32</td><td>alias for BGRA byte array of color data, for the current platform (>= SDL 2.0.5)</td></tr>
<tr><td>SDL_PIXELFORMAT_ABGR32</td><td>alias for ABGR byte array of color data, for the current platform (>= SDL 2.0.5)</td></tr>
<tr><td>SDL_PIXELFORMAT_YV12</td><td>planar mode: Y + V + U (3 planes)</td></tr>
<tr><td>SDL_PIXELFORMAT_IYUV</td><td>planar mode: Y + U + V (3 planes)</td></tr>
<tr><td>SDL_PIXELFORMAT_YUY2</td><td>packed mode: Y0+U0+Y1+V0 (1 plane)</td></tr>
<tr><td>SDL_PIXELFORMAT_UYVY</td><td>packed mode: U0+Y0+V0+Y1 (1 plane)</td></tr>
<tr><td>SDL_PIXELFORMAT_YVYU</td><td>packed mode: Y0+V0+Y1+U0 (1 plane)</td></tr>
<tr><td>SDL_PIXELFORMAT_NV12</td><td>planar mode: Y + U/V interleaved (2 planes) (>= SDL 2.0.4)</td></tr>
<tr><td>SDL_PIXELFORMAT_NV21</td><td>planar mode: Y + V/U interleaved (2 planes) (>= SDL 2.0.4)</td></tr>
</table>

---
Translated by [SteDeshain](https://github.com/SteDeshain)   
Reference to http://wiki.libsdl.org/SDL_RenderReadPixels