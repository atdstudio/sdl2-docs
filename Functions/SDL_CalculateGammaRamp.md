
# [SDL_CalculateGammaRamp](http：//wiki/libsdl.org/SDL_CalculateGammaRamp)

Use this function to calculate a 256 entry gamma ramp for a gamma value.

使用这个函数来计算伽玛值的256条伽玛斜度。

##  Syntax 语法

```c 
void SDL_CalculateGammaRamp(float   gamma,
                            Uint16* ramp)
```

## Function Parameters 函数参数

| 参数 | 解释（EN）| 解释（ZH）|
|------|---------|------------|
| gamma | a gamma value where 0.0 is black and 1.0 is identity | 其中黑色的伽玛值是0.0和1.0是同一值。|
| ramp | an array of 256 values filled in with the gamma ramp | 伽玛斜度是由256个值填充的。|

## Code Examples 示例代码

```c 
暂无
```

## Remarks 注意

```c
暂无 
```

## Related Functions 相关函数

[SDL_SetWindowGammaRamp](http：//wiki.libsdl.org/SDL_SetWindowGammaRamp)()


------------------------------------------------------------------------------
*[SixerME](https://github.com/DXkite) Translated*

