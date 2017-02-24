# [SDL_HINT_APPLE_TV_CONTROLLER_UI_EVENTS](http://wiki.libsdl.org/SDL_HINT_APPLE_TV_CONTROLLER_UI_EVENTS?highlight=%28%5CbCategoryDefine%5Cb%29%7C%28SGHints%29)

指定与Apple TV一起使用的控制器是否生成UI事件。

## 值
|值   |描述               |
|:--:|:------------------|
|0   |控制器输入不生成UI事件|
|1   |控制器输入生成UI事件  |

## 缺省
默认下控制器输入不生成UI事件

## 样例代码
```c 
You can add your code example here
```

## 备注
当UI事件由控制器输入生成时，当按下Apple TV遥控器的菜单按钮时，  
以及当按下游戏手柄上的暂停或B按钮时，应用程序将被在后台允许。
有关正确使用Apple TV控制器的更多信息，请参见：[Apple Developer](https://developer.apple.com/tvos/human-interface-guidelines/remote-and-controllers/)

## 版本
此提示自SDL 2.0.5开始提供。

----------------------------------------------------------------------------
*@[DXkite](https://github.com/DXkite) Translated.*
