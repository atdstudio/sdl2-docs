# [SDL_AndroidGetActivity](http://wiki.libsdl.org/SDL_AndroidGetActivity?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)

Use this function to retrieve the Java instance of the activity class in an Android application.
使用此函数可以在Android程序中获取Activity的JAVA对象实例。

## Syntax 语法
```c 
void* SDL_AndroidGetActivity(void)
```

## Return Value 返回值

Returns the jobject representing the instance of the Activity class of the Android application, or NULL on error.
如果成功则返回Android应用程序中的以jobject类型的Activity对象实例，出错则返回NULL。
The jobject returned by the function is a local reference and must be released by the caller. See the PushLocalFrame() and PopLocalFrame() or DeleteLocalRef() functions of the Java native interface (in Oracle's documentation).
由于函数返回的jobject类型是本地映射的，所以如果要释放的话就必须由调用者去释放。
##　Code Examples 代码示例

```c 
#include "SDL.h"
#include <jni.h>

// This example requires C++  这个示例需要使用C++
// Calls the void showHome() method of the Java instance of the activity. 调用无效的showHome()方法进行activity的JAVA实例。
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

The prototype of the function in SDL's code actually declares a void* return type, even if the implementation returns a jobject. The rationale being that it allows not to include jni.h in the headers of the SDL.
这个SDL函数原型实际上声明了void*的返回类型，甚至返回了jobject。值得注意的是允许SDL不包含jni.h的头文件。

## Version 版本

This function is available since SDL 2.0.0.
这个函数来自SDL 2.0.0

## Related Functions 相关函数

[SDL_AndroidGetJNIEnv](http://wiki.libsdl.org/SDL_AndroidGetJNIEnv)

--------------------------------------------------------------------------
*@[SixerMe](https://github.com/DXkite) Translated*