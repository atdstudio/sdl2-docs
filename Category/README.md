# Basic 基本库

| 信息|头文件|
|-----------------------|-------------------------|
|[Initialization and Shutdown 初始化和退出](Init.md)| [SDL.h](http://hg.libsdl.org/SDL/file/default/include/SDL.h)   |
| Configuration Variables 配置相关变量 | [SDL_hints.h](http://hg.libsdl.org/SDL/file/default/include/SDL_hints.h)|
| Error Handling 错误处理   |   [SDL_error.h](http://hg.libsdl.org/SDL/file/default/include/SDL_error.h)     |
| Log Handling 日志处理     | [SDL_log.h](http://hg.libsdl.org/SDL/file/default/include/SDL_log.h)         |
| Assertions 断言           | [SDL_assert.h](http://hg.libsdl.org/SDL/file/default/include/SDL_assert.h)       |
| Querying SDL Version 查询SDL版本 | [SDL_version.h](http://hg.libsdl.org/SDL/file/default/include/SDL_version.h)|


# Video 绘图相关
| 信息|头文件|
|-----------------------|-------------------------|
| Display and Window Management 显示和窗口管理     |[SDL_video.h](http://hg.libsdl.org/SDL/file/default/include/SDL_video.h)|
| 2D Accelerated Rendering 2D加速渲染   |[SDL_render.h](http://hg.libsdl.org/SDL/file/default/include/SDL_render.h) |
|Pixel Formats and Conversion Routines 像素相关转换操作|[SDL_pixels.h](http://hg.libsdl.org/SDL/file/default/include/SDL_pixels.h)|
| Rectangle Functions 矩形函数 |[SDL_rect.h](http://hg.libsdl.org/SDL/file/default/include/SDL_rect.h)|
| Surface Creation and Simple Drawing 表面的创建和简单绘制 | [SDL_surface.h](http://hg.libsdl.org/SDL/file/default/include/SDL_surface.h) |
| Platform-specific Window Management 平台相关的窗口管理 | [SDL_syswm.h](http://hg.libsdl.org/SDL/file/default/include/SDL_syswm.h)|
| Clipboard Handling 剪贴板处理 | [SDL_clipboard.h](http://hg.libsdl.org/SDL/file/default/include/SDL_clipboard.h) |

# Input Events 输入事件
| 信息|头文件|
|-----------------------|-------------------------|
| Event Handling 事件处理 | [SDL_events.h](http://hg.libsdl.org/SDL/file/default/include/SDL_events.h) |
| Keyboard Support 键盘支持 | [SDL_keyboard.h](http://hg.libsdl.org/SDL/file/default/include/SDL_keyboard.h) , [SDL_keycode.h](http://hg.libsdl.org/SDL/file/default/include/SDL_keycode.h),[SDL_scancode.h](http://hg.libsdl.org/SDL/file/default/include/SDL_scancode.h) |
| Mouse Support 鼠标支持    | [SDL_mouse.h](http://hg.libsdl.org/SDL/file/default/include/SDL_mouse.h) |
| Joystick Support 操纵杆支持 | [SDL_joystick.h](http://hg.libsdl.org/SDL/file/default/include/SDL_joystick.h) |
| Game Controller Support 游戏控制器支持 | [SDL_gamecontroller.h](http://hg.libsdl.org/SDL/file/default/include/SDL_gamecontroller.h)| 

# Force Feedback 重力感应
| 信息|头文件|
|-----------------------|-------------------------|
| Force Feedback Support 重力感应支持 | [SDL_haptic.h](http://hg.libsdl.org/SDL/file/default/include/SDL_haptic.h) |

# Audio 音频处理
| 信息|头文件|
|-----------------------|-------------------------|
| Audio Device Management, Playing and Recording 音频设备管理，音频播放和记录 | [SDL_audio.h](http://hg.libsdl.org/SDL/file/default/include/SDL_audio.h) |

# Threads 多线程

| 信息|头文件|
|-----------------------|-------------------------|
| Thread Management 线程管理 | [SDL_thread.h](http://hg.libsdl.org/SDL/file/default/include/SDL_thread.h) |
| Thread Synchronization Primitives 多线程同步，互斥体 | [SDL_mutex.h](http://hg.libsdl.org/SDL/file/default/include/SDL_mutex.h) |
| Atomic Operations 线程原子操纵 | [SDL_atomic.h](http://hg.libsdl.org/SDL/file/default/include/SDL_atomic.h)  |

# Timers 计时器
| 信息|头文件|
|-----------------------|-------------------------|
| Timer Support 计时器支持 | [SDL_timer.h](http://hg.libsdl.org/SDL/file/default/include/SDL_timer.h)|

# File Abstraction 文件抽象
| 信息|头文件|
|-----------------------|-------------------------|
| Filesystem Paths 文件系统路径 | [SDL_filesystem.h](http://hg.libsdl.org/SDL/file/default/include/SDL_filesystem.h) |
| File I/O Abstraction 文件抽象输入输出 |[SDL_rwops.h](http://hg.libsdl.org/SDL/file/default/include/SDL_rwops.h)|

# Shared Object Support 动态库支持 
*All by @[DXkite](https://github.com/DXkite)*

| 信息|头文件|
|-----------------------|-------------------------|
| [Shared Object Loading and Function Lookup 动态库的加载和函数的调用](SharedObject.md)| [SDL_loadso.h](http://hg.libsdl.org/SDL/file/default/include/SDL_loadso.h) |


# Platform and CPU Information 平台和CPU信息

| 信息|头文件|
|-----------------------|-------------------------|
| Platform Detection 平台检测 |[SDL_platform.h](http://hg.libsdl.org/SDL/file/default/include/SDL_platform.h)|
| CPU Feature Detection CPU特征检测 | [SDL_cpuinfo.h](http://hg.libsdl.org/SDL/file/default/include/SDL_cpuinfo.h) |
| Byte Order and Byte Swapping 字节顺和字节交换 |[SDL_endian.h](http://hg.libsdl.org/SDL/file/default/include/SDL_endian.h) |
| Bit Manipulation 位操作 |[SDL_bits.h](http://hg.libsdl.org/SDL/file/default/include/SDL_bits.h) |

# Power Management 电量管理
| 信息|头文件|
|-----------------------|-------------------------|
| Power Management Status 电量管理器状态 | [SDL_power.h](http://hg.libsdl.org/SDL/file/default/include/SDL_power.h) |

# Additional Functionality 额外的功能函数 
| 信息|头文件|
|-----------------------|-------------------------|
| Platform-specific Functionality 系统相关的函数扩展 | [SDL_system.h](http://hg.libsdl.org/SDL/file/default/include/SDL_system.h) |
| Standard Library Functionality 标准库相关的函数扩展 |[SDL_stdinc.h](http://hg.libsdl.org/SDL/file/default/include/SDL_stdinc.h) |

*@[DXkite](https://github.com/DXkite) Translated.*