### SDL_HasClipboardText

Use this function to get a flag indicating whether the clipboard exists and contains a text string that is non-empty.

使用此函数来获取一个标记，指示剪贴板中是否存在并包含一个文本字符串，非空。
#### Syntax **语法** 
包含在SDL_clipboard.h

SDL_bool SDL_HasClipboardText(void) 

#### Return Value **返回值** 

Returns SDL_TRUE if the clipboard has text, or SDL_FALSE if it does not.

返回SDL_TRUE如果剪贴板中有文本，否则返回SDL_FALSE。

#### Code Examples 
暂无

#### Remarks **备注**
暂无
 ####Version

This function is available since SDL 2.0.0.

#### Related Functions **相关函数** 

[SDL_GetClipboardText](http://wiki.libsdl.org/SDL_GetClipboardText)

[SDL_SetClipboardText](http://wiki.libsdl.org/SDL_SetClipboardText)


---
*@[PomeloSan](https://github.com/PomeloSan) Translated .*
