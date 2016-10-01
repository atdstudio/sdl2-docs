#[SDL_AudioFormat](https://wiki.libsdl.org/SDL_AudioFormat)
An enumeration of audio formats.  
音频格式的枚举值。

##Values 值
###Bit Meanings 位释意
These are what the 16 bits in [SDL_AudioFormat](SDL_AudioFormat.md) currently mean:  
以下是 [SDL_AudioFormat](SDL_AudioFormat.md) 中16位值的意义：
```
 +----------------------sample is signed if set（有符号）
 |
 |        +----------sample is bigendian if set（大端存储）
 |        |
 |        |           +--sample is float if set（浮点数）
 |        |           |
 |        |           |  +--sample bit size---+（采样的位大小）
 |        |           |  |                    |
15 14 13 12 11 10  9  8  7  6  5  4  3  2  1  0
```
Unspecified bits are always zero, but may be used in later versions of SDL. There are macros to query the specified bits.  
没有用到的位总是 0, 但在 SDL 未来的版本中可能会用到。

###Audio Format Macros 音频格式宏

<table>
<tr><td colspan="2" style="text-align: center;"><b>8-bit support 8位支持</b></td></tr>
<tr><td>AUDIO_S8</td><td>signed 8-bit samples 有符号8位采样</td></tr>
<tr><td>AUDIO_U8</td><td>unsigned 8-bit samples 无符号8位采样</td></tr>
<tr><td colspan="2" style="text-align: center;"><b>16-bit support 16位支持</b></td></tr>
<tr><td>AUDIO_S16LSB</td><td>signed 16-bit samples in little-endian byte order 小端有符号16位</td></tr>
<tr><td>AUDIO_S16MSB</td><td>signed 16-bit samples in big-endian byte order 大端有符号16位</td></tr>
<tr><td>AUDIO_S16SYS</td><td>signed 16-bit samples in native byte order 本机字节顺序有符号16位</td></tr>
<tr><td>AUDIO_S16</td><td>AUDIO_S16LSB</td></tr>
<tr><td>AUDIO_U16LSB</td><td>unsigned 16-bit samples in little-endian byte order 小端无符号16位</td></tr>
<tr><td>AUDIO_U16MSB</td><td>unsigned 16-bit samples in big-endian byte order 大端无符号16位</td></tr>
<tr><td>AUDIO_U16SYS</td><td>unsigned 16-bit samples in native byte order 本机字节顺序无符号16位</td></tr>
<tr><td>AUDIO_U16</td><td>AUDIO_U16LSB</td></tr>
<tr><td colspan="2" style="text-align: center;"><b>32-bit support (new to SDL 2.0) 32位支持（SDL2新增）</b></td></tr>
<tr><td>AUDIO_S32LSB</td><td>32-bit integer samples in little-endian byte order 小端32位整型</td></tr>
<tr><td>AUDIO_S32MSB</td><td>32-bit integer samples in big-endian byte order 大端32位整型</td></tr>
<tr><td>AUDIO_S32SYS</td><td>32-bit integer samples in native byte order 本机字节顺序32位整型</td></tr>
<tr><td>AUDIO_S32</td><td>AUDIO_S32LSB</td></tr>
<tr><td colspan="2" style="text-align: center;"><b>float support (new to SDL 2.0) 浮点支持（SDL2新增）</b></td></tr>
<tr><td>AUDIO_F32LSB</td><td>32-bit floating point samples in little-endian byte order 小端32位浮点</td></tr>
<tr><td>AUDIO_F32MSB</td><td>32-bit floating point samples in big-endian byte order 大端32位浮点</td></tr>
<tr><td>AUDIO_F32SYS</td><td>32-bit floating point samples in native byte order 本机字节顺序32位浮点</td></tr>
<tr><td>AUDIO_F32</td><td>AUDIO_F32LSB</td></tr>
</table>

###Audio Format Values 音频格式值
##Code Examples
```C
extern SDL_AudioFormat fmt;
if (SDL_AUDIO_ISFLOAT(fmt)) {
    printf("floating point data\n");
} else {
    printf("integer data\n");
}
printf("%d bits per sample\n", (int) SDL_AUDIO_BITSIZE(fmt));
```
##Remarks 注释
Be careful about assuming details of a data format. If you only check SDL_AUDIO_ISFLOAT(), you might be surprised to find a later version of SDL adds Float64 support when you expected there to be only 32-bit data, for example.  
对数据格式的详细信息要小心判断。例如你只检查 SDL_AUDIO_ISFLOAT(), 你可能会发现 SDL 在后来的版本中已经支持了64位浮点数而不是只有32位的数据。

##Related Structures 相关结构体
[SDL_AudioCVT](../Structures/SDL_AudioCVT.md)  
[SDL_AudioSpec](../Structures/SDL_AudioSpec.md)

##Related Functions 相关函数
[SDL_BuildAudioCVT](../Functions/SDL_BuildAudioCVT.md)  
[SDL_MixAudioFormat](../Functions/SDL_MixAudioFormat.md)

---
*@[lxfly2000](https://github.com/lxfly2000)*
