### SDL_GetClipboardText

Use this function to get UTF-8 text from the clipboard, which must be freed with SDL_free().
 
使用此功能可从剪贴板，必须以SDL_free释放获得UTF-8文本（）

####Syntax **语法** 
char* SDL_GetClipboardText(void) 

####Return Value **返回值 ** 

Returns the clipboard text on success or NULL on failure; call SDL_GetError() for more information.

返回上失败是成功还是空的剪贴板中的文本; 调用SDL_GetError（）了解更多信息。

#### Code Examples 

You can add your code example here 

#### Remarks **备注** 

This functions returns NULL if there was not enough memory left for a copy of the clipboard's content.

剪切板如果没有足够的内存留给副本该函数返回NULL。

#### Related Functions **相关函数** 

[SDL_HasClipboardText ](http://wiki.libsdl.org/SDL_HasClipboardText)

[SDL_SetClipboardText ](http://wiki.libsdl.org/SDL_SetClipboardText)

---
*@[PomeloSan](https://github.com/PomeloSan) Translated .*