# SDL_LoadFunction

Use this function to look up the address of the named function in the shared object and return it.
根据指定的名称在加载了共享库的内存区中找到指定的函数所在的地址，并返回他。

## Syntax 语法
```c
void* SDL_LoadFunction(void*       handle,
                       const char* name)
```

## Function Parameters 函数相关参数
| 参数名 |解释 |
|--------|-----|
| handle | a valid shared object handle returned by [SDL_LoadObject](http://wiki.libsdl.org/SDL_LoadObject)()  一个用函数 [SDL_LoadObject](SDL_LoadObject.md) 返回的可用共享库句柄 |
| name   | the name of the function to look up 要查找的函数的名称 |
## Return Value 返回值
Returns a pointer to the function or NULL if there was an error; call [SDL_GetError](http://wiki.libsdl.org/SDL_GetError)() for more information.
返回一个函数指针，如果发生错误则返回`NULL`,如果发生了错误，调用函数 [SDL_GetError](SDL_GetError.md)() 可获取更多错误信息。   

## Code Examples 代码示例

```c
#include "SDL_loadso.h"

// Variable declaration
void* myHandle = NULL;
char* myFunctionName = "myFancyFunction";
void (*myFancyFunction)(int anInt);

// Dynamically load mylib.so
myHandle = SDL_LoadObject("mylib.so");

// Load the exported function from mylib.so
// The exported function has the following prototype
// void myFancyFunction(int anInt);
myFancyFunction = (void (*)(int))SDL_LoadFunction(myHandle, myFunctionName);

// Call myFancyFunction with a random integer
if (myFancyFunction != NULL) {
    myFancyFunction(15);
} else {
    // Error handling here
}
```
 
## Remarks 注意

This function pointer is no longer valid after calling [SDL_UnloadObject](http://wiki.libsdl.org/SDL_UnloadObject).
函数指针在调用 [SDL_UnloadObject](SDL_UnloadObject.md)函数后会失效。
This function can only look up C function names. Other languages may have name mangling and intrinsic language support that varies from compiler to compiler.
这个函数只适合查找C语言函数名，其他语言。根据编译器的不同，其他语言可能会有名称的修正和内置语言的修正。
Make sure you declare your function pointers with the same calling convention as the actual library function. Your code will crash mysteriously if you do not do this.
请确保你的函数指针和共享库中相关函数具有相同的函数格式声明，不然你的程序可能会莫名其妙的崩溃。

##  Related Functions 相关函数

[SDL_LoadObject](SDL_LoadObject.md)

[SDL_UnloadObject](SDL_UnloadObject.md)

*@[DXkite](https://github.com/DXkite) Translated.*