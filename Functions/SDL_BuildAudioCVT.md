# [SDL_BuildAudioCVT](http://wiki.libsdl.org/SDL_BuildAudioCVT)

Use this function to initialize an SDL_AudioCVT structure for conversion.
使用这个函数初始化[SDL_AudioCVT](http://wiki.libsdl.org/SDL_AudioCVT)结构以进行转换。

## Syntax 语法

```c
int SDL_BuildAudioCVT(SDL_AudioCVT*   cvt,
                      SDL_AudioFormat src_format,
                      Uint8           src_channels,
                      int             src_rate,
                      SDL_AudioFormat dst_format,
                      Uint8           dst_channels,
                      int             dst_rate)
```

## Function Parameters 函数参数

| 参数值 |  解释（EN） |  解释（ZH） |
|--------|------------|------------|
| cvt | an [SDL_AudioCVT](http://wiki.libsdl.org/SDL_AudioCVT) structure filled in with audio conversion information |  一个用音频转换信息填充的 [SDL_AudioCVT](http://wiki.libsdl.org/SDL_AudioCVT)结构.|
| src_format | the source format of the audio data; for more info see [SDL_AudioFormat](http://wiki.libsdl.org/SDL_AudioFormat) | 音频数据的源格式;详情查看[SDL_AudioFormat](http://wiki.libsdl.org/SDL_AudioFormat).|
| src_channels | the number of channels in the source | 源中的通道数.|
| src_rate | the frequency (samples-frames-per-second) of the source | 源的频率（每秒采样帧数）.|
| dst_format | the destination format of the audio data; for more info see [SDL_AudioFormat](http://wiki.libsdl.org/SDL_AudioFormat) | 音频数据的目标格式 ; 详情查看[SDL_AudioFormat](http://wiki.libsdl.org/SDL_AudioFormat).|
| dst_channels | the number of channels in the destination | 目标的通道数.|
| dst_rate | the frequency (samples-frames-per-second) of the destination | 目标的频率 (每秒采样帧数).|

## Return Value 返回值

Returns 1 if the audio filter is prepared, 0 if no conversion is needed, or a negative error code on failure; call [SDL_GetError](http;//wiki.libsdl.org/SDL_GetError)() for more information.

如果音频准备填充则返回 1 , 如果不需要转换则返回 0 ,或否定失败的错误代码; 调用 [SDL_GetError](http;//wiki.libsdl.org/SDL_GetError)() 查看更多。|

## Code Examples 代码示例

```c
Toggle line numbers
// Change 1024 stereo sample frames at 48000Hz from float32 to int16.
SDL_AudioCVT cvt;
SDL_BuildAudioCVT(&cvt, AUDIO_F32, 2, 48000, AUDIO_S16, 2, 48000);
SDL_assert(cvt.needed); // obviously, this one is always needed.
cvt.len = 1024 * 2 * 4;  // 1024 stereo float32 sample frames.
cvt.buf = (Uint8 *) SDL_malloc(cvt.len * cvt.len_mult);
// read your float32 data into cvt.buf here.
SDL_ConvertAudio(&cvt);
// cvt.buf has cvt.len_cvt bytes of converted data now.
```

## Remarks 注意

Before an [SDL_AudioCVT](httpp;//wiki.libsdl.org/SDL_AudioCVT)() structure can be used to convert audio data it must be initialized with source and destination information.

在可以使用SDL_AudioCVT结构转换音频数据之前，必须使用源和目标信息进行初始化。

This function will zero out every field of the [SDL_AudioCVT](httpp;//wiki.libsdl.org/SDL_AudioCVT)(), so it must be called before the application fills in the final buffer information.

此函数将清零[SDL_AudioCVT](httpp;//wiki.libsdl.org/SDL_AudioCVT)()的每个字段。

Once this function has returned successfully, and reported that a conversion is necessary, the application fills in the rest of the fields in [SDL_AudioCVT](httpp;//wiki.libsdl.org/SDL_AudioCVT)(), now that it knows how large a buffer it needs to allocate, and then can call [SDL_ConvertAudio](http;//wiki.libsdl.org/SDL_ConvertAudio)（） to complete the conversion.

一旦此函数成功返回后，并报告需要进行转换，该应用程式将填充[SDL_AudioCVT](httpp;//wiki.libsdl.org/SDL_AudioCVT)()的其余字段，现在它知道它需要分配多大的缓冲区，然后可以调用[SDL_ConvertAudio](http;//wiki.libsdl.org/SDL_ConvertAudio)（）来完成转换。

## Related Functions 相关函数

[SDL_ConvertAudio](http://wiki.libsdl.org/SDL_ConvertAudio)


---------------------------------------------------------------
*[SixerME](https://github.com/DXkite) Translated*