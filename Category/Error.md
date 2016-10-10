# Error Handling

## Introduction 介绍
 
Functions in this category provide simple error message routines for SDL. 
本分类中的函数提供了一个简单的SDL错误信息处理函数
[SDL_GetError](../Functions/SDL_GetError.md) can be called for almost all SDL functions to determine what problems are occurring. 
[SDL_GetError](../Functions/SDL_GetError.md) 可以在大多数的SDL函数中调用，用来提示错误。
Check the wiki page of each specific SDL function to see whether [SDL_GetError](../Functions/SDL_GetError.md) is meaningful for them or not.
在一些函数调用失败的时候,[SDL_GetError](../Functions/SDL_GetError.md)可以提供详细的错误信息。
The SDL error messages are in English.
提示的错误信息是英文的。





## Functions 函数

[SDL_ClearError](../Functions/SDL_ClearError.md)	
[SDL_GetError](../Functions/SDL_GetError.md)	
[SDL_SetError](../Functions/SDL_SetError.md)	

-------------------------------------------------------------------
*@[DXkite](https://github.com/DXkite) Translated.*