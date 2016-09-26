# Initialization and Shutdown 初始化和退出
 
## Introduction 介绍
The functions in this category are used to set up SDL for use and generally have global effects in your program.
在本分类中将要出现的函数是用来进行全局和使用的设置。
## Introduction to Initialization 初始化的介绍
To begin using SDL in your program SDL_Init() must be called before most other SDL functions. The role of SDL_Init() is to properly initialize the SDL library and start each of the various subsystems requested as part of the call.
在使用其他的SQL函数之前，你必须最先调用函数 [SDL_Init](../Functions/SDL_Init.md) 对系统进行初始化，[SDL_Init](../Functions/SDL_Init.md)的作用是适当的初始化一些SDL库的各类子系统。
{i} The File I/O and Threading subsystems are initialized by default. To initialize other subsystems you must specifically call them. Multiple subsystems may be OR'd together.
*注：文件I/O和线程是默认被初始化的，要想唤起初始化其他的子系统，你必须一个一个的调用，可以用|来初始化多个子系统。
*Example 例子*
```c
SDL_Init(SDL_INIT_VIDEO|SDL_INIT_AUDIO);
```
This initializes the 2 default subsystems plus the Video, Audio, and Event Handling subsystems.
这个初始化调用显示初始化了2个默认的系统，还有图形、音频、事件处理系统。
The Event Handling subsystem is initialized implicitly by the Video subsystem.
在初始化图形系统的时候会隐式初始化事件处理系统。
It should be noted that on some operating systems, SDL_Init() will fail if SDL_main() has not been defined as the entry point for the program.
在某些操作系统中，[SDL_Init](../Functions/SDL_Init.md)函数在`SDL_main()`函数没被定义成程序的入口点的时候会调用失败。
Calling SDL_SetMainReady() prior to SDL_Init() will circumvent this failure condition,
在这种情况下，需要在函数 [SDL_Init](../Functions/SDL_Init.md) 前调用函数 [SDL_SetMainReady](../Functions/SDL_SetMainReady.md)，
however, users should be careful when calling SDL_SetMainReady() as improper initialization may cause crashes and hard to diagnose problems. 
尽管如此，你还是需要注意一下不正常初始化调用函数 [SDL_SetMainReady](../Functions/SDL_SetMainReady.md)后 ，可能导致的崩溃和难以诊断的问题。

## Introduction to Shut Down 关闭的介绍

SDL_Quit() should be called before an SDL application exits to safely shut down all subsystems, including the default ones.
在SDL程序退出之前，必须调用函数[SDL_Quit](../Functions/SDL_Quit.md)来关闭包括默认的子系统的所有子系统。
It is not necessary to specify individual subsystems when using SDL_Quit() as it will automatically shut down all active subsystems.
在调用 [SDL_Quit](../Functions/SDL_Quit.md) 的时候，不需要特定的指出要关闭那些系统，他会自动管关闭所有激活的子系统。



# Functions 函数集
1. [SDL_Init](../Functions/SDL_Init.md)
2. [SDL_InitSubSystem](../Functions/SDL_InitSubSystem.md)
3. [SDL_Quit](../Functions/SDL_Quit.md)
4. [SDL_QuitSubSystem](../Functions/SDL_QuitSubSystem.md)
5. [SDL_SetMainReady](../Functions/SDL_SetMainReady.md)
6. [SDL_WasInit](../Functions/SDL_WasInit.md)
7. [SDL_WinRTRunApp](../Functions/SDL_WinRTRunApp.md)

-------------------------------------------------------------------
*@[DXkite](https://github.com/DXkite) Translated.*