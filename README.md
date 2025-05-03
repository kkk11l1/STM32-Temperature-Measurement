# STM32双波长测温系统

## 项目说明
基于STM32的双波长测温系统，使用850nm和900nm波长进行温度测量。通过普朗克辐射定律计算温度，实现高温测量。

## 功能特点
- 双波长测温（850nm和900nm）
- 串口通信（115200波特率）
- 实时温度显示
- 支持高温测量（最高2000K）

## 文件结构
```
STM32-Temperature-Measurement/
├── User/                  # 用户代码
│   ├── main.c            # 主程序
│   ├── usart.c           # 串口配置
│   ├── usart.h           # 串口头文件
│   ├── gpio.c            # GPIO配置
│   ├── gpio.h            # GPIO头文件
│   ├── system_stm32f1xx.c # 系统时钟配置
│   ├── error_handler.c   # 错误处理
│   └── retarget.c        # printf重定向
├── Drivers/              # STM32驱动
│   ├── CMSIS/           # CMSIS核心
│   └── STM32F1xx_HAL_Driver/ # HAL驱动
└── Startup/             # 启动文件
```

## 硬件要求
- STM32F103C8T6开发板
- 8MHz外部晶振
- USB转串口模块
- 串口调试助手(SSCOM)

## 软件要求
- Keil MDK uVision5
- STM32F1xx HAL库
- MATLAB（用于数据生成）

## 使用说明
1. 硬件连接
   - 连接STM32的PA9(TX)到串口模块的RX
   - 连接STM32的PA10(RX)到串口模块的TX
   - 连接GND
   - 确保外部晶振正确连接

2. 软件配置
   - 使用Keil MDK打开项目
   - 配置串口调试助手（115200波特率）
   - 运行MATLAB程序生成测试数据

3. 运行步骤
   - 编译并下载程序到STM32
   - 运行MATLAB程序发送数据
   - 观察串口调试助手显示的温度值

## 注意事项
1. 确保外部晶振频率为8MHz
2. 串口通信波特率为115200
3. 温度计算使用牛顿迭代法，可能需要根据实际需求调整精度

## 许可证
MIT License

## 联系方式
如有问题，请提交Issue或Pull Request。
