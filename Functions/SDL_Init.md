# SDL_Init
Use this function to initialize the SDL library. This must be called before using any other SDL function.   
使用这个函数可以初始化SDL库，在使用SDL其他的库函数之前必须被调用。


## Syntax 语法
```c 
int SDL_Init(Uint32 flags)
```
## Function Parameters 函数相关参数
| 参数名 |解释 |
|--------|-----|
|flags | subsystem initialization flags; see Remarks for details 子系统初始化标志，看 [Remarks 注意](#Remarks 注意) 了解跟多消息。|

## Return Value 返回值

Returns 0 on success or a negative error code on failure; call SDL_GetError() for more information.     
返回0成功，负数则失败，可以通过调用函数 [SDL_GetError](SDL_GetError.md) 获取错误详情。
## Code Examples 代码示例
### C
```c
#include "SDL.h"
#include <stdio.h> /* for fprintf() */
#include <stdlib.h> /* for atexit() */

int main(int argc, char** argv) {
    if (SDL_Init(SDL_INIT_VIDEO|SDL_INIT_TIMER) != 0) {
        fprintf(stderr,
                "\nUnable to initialize SDL:  %s\n",
                SDL_GetError()
               );
        return 1;
    }
    atexit(SDL_Quit);

    /* ... */

    return 0;
}
```
### C++
```c++
切换行号显示
#include <exception>
#include <string>
#include "SDL.h"

class InitError: public std::exception {
    public:
        InitError();
        InitError(const std::string&);
        virtual ~InitError() throw();
        virtual const char* what() const throw();
    private:
        std::string msg;
};

InitError::InitError():
  exception(), msg(SDL_GetError()) {}
InitError::InitError(const std::string& m):
  exception(), msg(m) {}
InitError::~InitError() throw() {}
const char* InitError::what() const throw() {
    return msg.c_str();
}

class SDL {
    public:
        SDL(Uint32 flags = 0) throw(InitError);
        virtual ~SDL();
};

SDL::SDL(Uint32 flags) throw(InitError) {
    if (SDL_Init(flags) != 0)
        throw InitError();
}

SDL::~SDL() {
    SDL_Quit();
}

/* ... */

#include <iostream>

int main(int argc, char **argv) {
    try {
        SDL sdl(SDL_INIT_VIDEO|SDL_INIT_TIMER);

        /* ... */

        return 0;
    }

    catch (const InitError& err) {
        std::cerr
            << "Error while initializing SDL:  "
            << err.what() << std::endl;
    }

    return 1;
}
```

## Remarks 注意

SDL_Init() simply forwards to calling SDL_InitSubSystem(). 

Therefore, the two may be used interchangeably. 

Though for readability of your code SDL_InitSubSystem() might be preferred.

The File I/O and Threading subsystems are initialized by default. 

You must specifically initialize other subsystems if you use them in your application.

flags may be any of the following OR'd together:

|初始标志|解释|
|-------|----|
|SDL_INIT_TIMER | timer subsystem|
|SDL_INIT_AUDIO|audio subsystem|
|SDL_INIT_VIDEO|video subsystem. Automatically initializes the SDL_INIT_EVENTS subsystem|
|SDL_INIT_JOYSTICK|joystick subsystem|
|SDL_INIT_HAPTIC|haptic (force feedback) subsystem|
|SDL_INIT_GAMECONTROLLER|controller subsystem. Automatically initializes the SDL_INIT_JOYSTICK subsystem|
|SDL_INIT_EVENTS|events subsystem|
|SDL_INIT_EVERYTHING |all of the above subsystems|
|SDL_INIT_NOPARACHUTE|compatibility; this flag is ignored|

If you want to initialize subsystems separately you would call SDL_Init(0) followed by SDL_InitSubSystem() with the desired subsystem flag.

## Related Functions 相关函数
1. [SDL_InitSubSystem](SDL_InitSubSystem.md)
2. [SDL_Quit](SDL_Quit.md)
3. [SDL_SetMainReady](SDL_SetMainReady.md)
4. [SDL_WasInit](SDL_WasInit.md)
