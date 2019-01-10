HttpEmptyGif模块
```
在内存中常驻了一个1*1的透明GIF图像，可以被非常快速的调用

    location = /_.gif{
        : empty_gif;
    }

empty_gif >

```