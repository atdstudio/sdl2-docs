####SDL_GameControllerAddMapping

Use this function to add support for controllers that SDL is unaware of or to cause an existing controller to have a different binding.

使用此功能来添加对控制器的支持，SDL是不知道或导致现有控制器有不同的结合。

####Syntax **语法** 
int SDL_GameControllerAddMapping(const char* mappingString) 

####Function Parameters **函数参数** 
| 参数| 描述|
|:----------:|:----------:|
|mappingString    |   the mapping string; see below映射字符串，见下文    |

####Return Value  **返回值** 

Returns 1 if a new mapping is added, 0 if an existing mapping is updated, -1 on error;
 callSDL_GetError() for more information.

果一个新的映射添加，0如果现有的映射更新，-1错误，则返回1; 调用SDL_GetError（）了解更多信息。

####Code Examples **代码** 

You can add your code example here 

####Remarks **备注** 

The mapping string has the format "GUID,name,mapping", where GUID is the string value fromSDL_JoystickGetGUIDString(), name is the human readable string for the device and mappings are controller mappings to joystick ones. Under Windows there is a reserved GUID of "xinput" that covers all XInput devices. The mapping format for joystick is:

射字符串的格式为“GUID，名称，映射”，其中GUID是从字符串值SDL_JoystickGetGUIDString（），名称是设备的人类可读的字符串，映射是控制器映射操纵杆的。在Windows下有一个涵盖所有XINPUT设备“XINPUT”的保留GUID。操纵杆的映射格式为：

| 属性 | 描述 |
|:----------:|:----------:|
|    bX    |    a joystick button, index X操纵杆按钮，指标X    |
|    hX.Y    |    hat X with value Y帽子x具有值Y   |
|    aX    |    axis X of the joystick操纵杆轴线    |

Buttons can be used as a controller axes and vice versa.
按钮可用于作为控制器的轴，反之亦然。

This string shows an example of a valid mapping for a controller:

此字符串示出了用于控制装置的有效映射的一例子："341a3608000000000000504944564944,Afterglow PS3 Controller,a:b1,b:b2,y:b3,x:b0,start:b9,guide:b12,back:b8,dpup:h0.1,dpleft:h0.8,dpdown:h0.4,dpright:h0.2,leftshoulder:b4,rightshoulder:b5,leftstick:b10,rightstick:b11,leftx:a0,lefty:a1,rightx:a2,righty:a3,lefttrigger:b6,righttrigger:b7"

“341a3608000000000000504944564944，余辉PS3控制器，：B1，B：B2，Y：B3，X：B0，启动：B9，指南：B12，回：B8，​​dpup：h0.1，dpleft：h0.8，dpdown：H0 4，dpright：h0.2，leftshoulder：B4，rightshoulder：B5，leftstick：B10，rightstick：B11，leftx：A0，左撇子：A1，rightx：A2，用右手：A3，lefttrigger：B6，righttrigger：B7“



####Related Functions**相关函数**

SDL_GameControllerMapping

SDL_GameControllerMappingForGUID

---
*@[PomeloSan](https://github.com/PomeloSan) Translated .*