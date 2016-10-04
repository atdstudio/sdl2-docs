# [SDL_AndroidGetJNIEnv](http://wiki.libsdl.org/SDL_AndroidGetJNIEnv?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)

Use this function to retrieve the Java native interface object (JNIEnv) of the current thread on Android builds.
该函数可以使Android的线程基础上检索Java的本地接口对象(JNIEnv).

## Syntax 语法
 ```c 
void* SDL_AndroidGetJNIEnv(void)
```

## Return Value 返回值

Returns a pointer to Java native interface object (JNIEnv) to which the current thread is attached, or 0 on error.
返回一个指针，在当前的线程中连接Java本地接口对象(JNIEnv).
## Code Examples 代码示例
```c 
#include "SDL.h"
#include <jni.h>

// This example requires C++

// Calls the void showHome() method of the Java instance of MyActivity.
void showHome(void)
{
    // retrieve the JNI environment.
    JNIEnv* env = (JNIEnv*)SDL_AndroidGetJNIEnv();

    // retrieve the Java instance of the SDLActivity
    jobject activity = (jobject)SDL_AndroidGetActivity();

    // find the Java class of the activity. It should be SDLActivity or a subclass of it.
    jclass clazz(env->GetObjectClass(activity));

    // find the identifier of the method to call
    jmethodID method_id = env->GetMethodID(clazz, "showHome", "()V");

    // effectively call the Java method
    env->CallVoidMethod(activity, method_id);

    // clean up the local references.
    env->DeleteLocalRef(activity);
    env->DeleteLocalRef(clazz);

    // Warning (and discussion of implementation details of SDL for Android):
    // Local references are automatically deleted if a native function called
    // from Java side returns. For SDL this native function is main() itself.
    // Therefore references need to be manually deleted because otherwise the
    // references will first be cleaned if main() returns (application exit).
}
```

## Remarks 注意

The prototype of the function in SDL's code actually declare a void* return type, even if the implementation returns a pointer to a JNIEnv. The rationale being that it allows not to include jni.h in the headers of the SDL.
在SDL的函数原型中已经声明了返回类型是void*, 即使实现返回了JNIEnv的指针，但是它允许不包含在SDL的 <jni.h> 头文件中
## Version 版本

This function is available since SDL 2.0.0.
该函数出自 SDL 2.0.0

## Related Functions 相关函数

[SDL_AndroidGetActivity](http://wiki.libsdl.org/SDL_AndroidGetActivity)

---------------------------------------------------------------------------------
*@[SixerMe](https://github.com/DXkite) Translated*