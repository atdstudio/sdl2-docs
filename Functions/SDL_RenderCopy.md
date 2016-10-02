#[SDL_RenderCopy](https://wiki.libsdl.org/SDL_RenderCopy)
Use this function to copy a portion of the texture to the current rendering target.  
使用该函数复制材质图像的一部分至当前的渲染目标。

##Syntax 语法
```C
int SDL_RenderCopyEx(SDL_Renderer*   renderer,
                     SDL_Texture*    texture,
                     const SDL_Rect* srcrect,
                     const SDL_Rect* dstrect)
```
##Function Parameters 函数参数
<table>
<tr><td><b>renderer</b></td><td>the rendering context<br/>渲染器</td></tr>
<tr><td><b>texture</b></td><td>the source texture; see <a href="#remarks-注释">Remarks</a> for details<br/>源材质，详细请看<a href="#remarks-注释">注释</a>。</td></tr>
<tr><td><b>srcrect</b></td><td>the source <a href="../Structures/SDL_Rect.md">SDL_Rect</a> structure or NULL for the entire texture<br/><a href="../Structures/SDL_Rect.md">SDL_Rect</a> 结构体指定的要复制的源材质的矩形区域或者 NULL 为整个材质图像。</td></tr>
<tr><td><b>dstrect</b></td><td>the destination <a href="../Structures/SDL_Rect.md">SDL_Rect</a> structure or NULL for the entire rendering target<br/><a href="../Structures/SDL_Rect.md">SDL_Rect</a> 结构体指定的目标矩形区域或者 NULL 为渲染器的整个区域。</td></tr>
</table>
##Return Value 返回值
Returns 0 on success or a negative error code on failure; call [SDL_GetError](SDL_GetError.md)() for more information.  
成功返回 0, 否则返回一个负数的错误码；调用 [SDL_GetError](SDL_GetError.md)() 获取更多信息。
##Code Examples 代码示例
```C
#include "SDL.h"
#define SHAPE_SIZE 16

int main(int argc, char *argv[])
{
  SDL_Window* Main_Window;
  SDL_Renderer* Main_Renderer;
  SDL_Surface* Loading_Surf;
  SDL_Texture* Background_Tx;
  SDL_Texture* BlueShapes;

  /* 指定要渲染的材质矩形区域和目标渲染区域 */
  SDL_Rect SrcR;
  SDL_Rect DestR;

  SrcR.x = 0;
  SrcR.y = 0;
  SrcR.w = SHAPE_SIZE;
  SrcR.h = SHAPE_SIZE;

  DestR.x = 640 / 2 - SHAPE_SIZE / 2;
  DestR.y = 580 / 2 - SHAPE_SIZE / 2;
  DestR.w = SHAPE_SIZE;
  DestR.h = SHAPE_SIZE;


  /* 渲染前创建一个窗口和渲染器 */
  Main_Window = SDL_CreateWindow("SDL_RenderCopy Example",
  SDL_WINDOWPOS_UNDEFINED, SDL_WINDOWPOS_UNDEFINED, 640, 580, 0);
  Main_Renderer = SDL_CreateRenderer(Main_Window, -1, SDL_RENDERER_ACCELERATED);

  /* 加载一幅图像，为了使用硬件加速渲染，把得到的 Surface 格式图像转换成材质图像 */
  Loading_Surf = SDL_LoadBMP("Background.bmp");
  Background_Tx = SDL_CreateTextureFromSurface(Main_Renderer, Loading_Surf);
  SDL_FreeSurface(Loading_Surf); /* we got the texture now -> free surface */

  /* 加载其他图像 */
  Loading_Surf = SDL_LoadBMP("Blueshapes.bmp");
  BlueShapes = SDL_CreateTextureFromSurface(Main_Renderer, Loading_Surf);
  SDL_FreeSurface(Loading_Surf);

  /* 这里是重点。该操作在屏幕中间渲染一个旋转的蓝色图形选中区域 */
  int i;
  int n;
  for (i = 0; i < 2; ++i) {
    for(n = 0; n < 4; ++n) {
      SrcR.x = SHAPE_SIZE * (n % 2);
      if (n > 1) {
        SrcR.y = SHAPE_SIZE;
      } else {
        SrcR.y = 0;
      }

      /* 渲染背景，NULL 为使用默认的值 */
      SDL_RenderCopy(Main_Renderer, Background_Tx, NULL, NULL);

      /* 渲染这个图形的动画 */
      SDL_RenderCopy(Main_Renderer, BlueShapes, &SrcR, &DestR);
      SDL_RenderPresent(Main_Renderer);
      SDL_Delay(500);
    }
  }


  /* 渲染器工作起来跟一个画布很像：
  当你执行 RenderCopy() 的时候你在往上面添加图像，每次绘制在最上方；
  你可以指定新图像的混合模式；
  渲染完成后使用 SDL_RenderPresent() 将画面显示到程序窗口。*/

  /* SDL 1.2 的提示：如果你习惯了 1.2 中的表面和 Blit 而对渲染器不是很明白的话，
  你可以把它当成你的主表面，SDL_RenderCopy() 就相当于把材质图像 Blit 到主表面，
  SDL_RenderPresent() 就相当于以前的 SDL_Flip() 函数。*/

  SDL_DestroyTexture(BlueShapes);
  SDL_DestroyTexture(Background_Tx);
  SDL_DestroyRenderer(Main_Renderer);
  SDL_DestroyWindow(Main_Window);
  SDL_Quit();


  return 0;
}
```
##Remarks 注释
The texture is blended with the destination based on its blend mode set with [SDL_SetTextureBlendMode](SDL_SetTextureBlendMode.md)().  
渲染后的材质根据 [SDL_SetTextureBlendMode](SDL_SetTextureBlendMode.md)() 的设置会带有混合效果。

The texture color is affected based on its color modulation set by [SDL_SetTextureColorMod](SDL_SetTextureColorMod.md)().  
材质的颜色是受 [SDL_SetTextureColorMod](SDL_SetTextureColorMod.md)() 影响的。

The texture alpha is affected based on its alpha modulation set by [SDL_SetTextureAlphaMod](SDL_SetTextureAlphaMod.md)().  
材质的透明度是受 [SDL_SetTextureAlphaMod](SDL_SetTextureAlphaMod.md)() 影响的。
##Related Functions 相关函数
[SDL_RenderCopyEx](SDL_RenderCopyEx.md)  
[SDL_SetTextureAlphaMod](SDL_SetTextureAlphaMod.md)  
[SDL_SetTextureBlendMode](SDL_SetTextureBlendMode.md)  
[SDL_SetTextureColorMod](SDL_SetTextureColorMod.md)

---
*@[lxfly2000](https://github.com/lxfly2000)*
