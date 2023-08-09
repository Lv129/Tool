# UART2OLED
## 效果

![image](https://github.com/Lv129/Tool/assets/48917882/c6a7a032-944e-402d-86ef-6cbe7a674b55)
## MCU/SOC
发送0xA5 0xA5后发送1024字节OLED数据，再发送0x5A 0x5A
参考
```c
// 包头 0xA5 0xA5
c = 0xA5;
printf("%c", c);
printf("%c", c);

// OLED_FrameBuffer 1024
for (i = 0; i < 8; i++)
{
    for (j = 0; j < 128; j++)
    {
        printf("%c", OLED_FrameBuffer[i][j]);
    }
}

// 包尾 0x5A 0x5A
c = 0x5A;
printf("%c", c);
printf("%c", c);
```

## 窗口程序
可在config/setup.txt中设置按钮控件、滑条控件的名字，以及他们发送的东西
![image](https://github.com/Lv129/Tool/assets/48917882/a0473f7d-c447-41c4-9a56-9066d2f25044)
