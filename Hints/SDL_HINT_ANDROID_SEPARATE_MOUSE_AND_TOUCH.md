# [SDL_HINT_ANDROID_SEPARATE_MOUSE_AND_TOUCH](http://wiki.libsdl.org/SDL_HINT_ANDROID_SEPARATE_MOUSE_AND_TOUCH?highlight=%28%5CbCategoryDefine%5Cb%29%7C%28SGHints%29)

指定控制是否鼠标和触屏事件一起或分开处理
## 值
|值   |描述                                                 |
|:--:|:------------------------------------------------|
|0   |鼠标事件将作为触摸事件处理，触摸将提高假鼠标事件       |
|1   |指定一个变量来控制鼠标和触摸事件是一起处理还是分开处理。|

## 缺省
默认下鼠标事件将作为触摸事件处理，触摸将提高假鼠标事件。  

## 样例代码
```c 
You can add your code example here
```

## 备注
此提示的值在运行时使用，因此可以随时更改。

## 版本
此提示自SDL 2.0.4起可用。

----------------------------------------------------------------------------
*@[DXkite](https://github.com/DXkite) Translated.*
