# [SDL_AllocRW](http://wiki.libsdl.org/SDL_AllocRW?highlight=%28%5CbCategoryAPI%5Cb%29%7C%28SDLFunctionTemplate%29)
 Use this function to allocate an empty, unpopulated [SDL_RWops](http://wiki.libsdl.org/SDL_RWops) structure.
使用这个函数可以在内存中分配一个空的[SDL_RWops](http://wiki.libsdl.org/SDL_RWops) 结构函数。
## Syntax 语法

```c 
SDL_RWops* SDL_AllocRW(void)
```
## Return Value 返回值

Returns a pointer to the allocated memory on success, or NULL on failure; call SDL_GetError() for more information.
返回内存的指针代表成功，NULL则是失败；调用[SDL_GetError](http://wiki.libsdl.org/SDL_GetError)()查看更多信息。
## Code Examples 代码示例
```c 
/* These functions should not be used except from pointers in an SDL_RWops 这个函数只能在SDL_RWops中使用 */
static int myseekfunc(SDL_RWops *context, int offset, int whence)
{
  return SDL_SetError("Can't seek in this kind of SDL_RWops");
}

static int myreadfunc(SDL_RWops *context, void *ptr, int size, int maxnum)
{
  SDL_memset(ptr,0,size*maxnum);
  return maxnum;
}

static int mywritefunc(SDL_RWops *context, const void *ptr, int size, int num)
{
  return num;
}

static int myclosefunc(SDL_RWops *context)
{
  if(context->type != 0xdeadbeef)
  {
    return SDL_SetError("Wrong kind of SDL_RWops for myclosefunc()");
  }

  free(context->hidden.unknown.data1);
  SDL_FreeRW(context);
  return 0;
}

SDL_RWops *MyCustomRWop()
{
  SDL_RWops *c=SDL_AllocRW();
  if(c==NULL) return NULL;

  c->seek =myseekfunc;
  c->read =myreadfunc;
  c->write=mywritefunc;
  c->close=myclosefunc;
  c->type =0xdeadbeef;
  c->hidden.unknown.data1=malloc(256);
  return c;
}
```
## Remarks 注意

Applications do not need to use this function unless they are providing their own SDL_RWops implementation. If you just need a SDL_RWops to read/write a common data source, you should use the built-in implementations in SDL, like SDL_RWFromFile() or SDL_RWFromMem(), etc.
如果应用程序不需要这个函数的话，那他们就要提供自己的[SDL_RWops](http://wiki.libsdl.org/SDL_RWops)去实现这个功能。如果你只需要SDL_RWops 进行读写的通用数据源，你应该使用内置SDL的去实现，像[SDL_RWFromFile](http://wiki.libsdl.org/SDL_RWFromMem)()或者[SDL_RWF](http://wiki.libsdl.org/SDL_RWFromMem)()等。

You must free the returned pointer with SDL_FreeRW(). Depending on your operating system and compiler, there may be a difference between the malloc() and free() your program uses and the versions SDL calls internally. Trying to mix the two can cause crashing such as segmentation faults. Since all SDL_RWops must free themselves when their close method is called, all SDL_RWops must be allocated through this function, so they can all be freed correctly with SDL_FreeRW().
你必须释放[SDL_FromRW](http://wikilibsdl.org/SDL_FromRW)()的指针，根据你的操作系统和编译器，有可能是mallo()和free()的程序使用和SDL内部调用版本之间的差异。

## Related Functions 相关函数

[SDL_FreeRW](http://wikilibsdl.org/SDL_FromRW)

-----------------------------------------------------------------
*@[SixerMe](https://github.com/DXkite) Translated*