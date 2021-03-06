
# STM32F103C8T6-SI4432_SMT点对点无线透传

> 时间 2015年 2月20日

> 测试者：Haven 

> SI4432型号:XL_4432-SMT（板载弹簧天线）

> 底板电路：借用 QS_TS1630_CTRL_V1.2_MB电路板

> 程序可配置0.96′OLED

> OLED型号：0.96寸 四线SPI接口（模拟SPI）  七脚排针


### 最终目地：

1. 采用串口1与外部进行通信，可传输接收任意长度数据;
2. 将接收后的数据无条件发送给指定地址的si4422模块;
3. 接收模块收到数据后无条件的将有效数据通过串口1的DMA传出；即：基于SI4432的点对点串口透传模块
 

### 实现功能：

首次实现SI4432的无线通信功能，上电后模块皆为接受状态，当PA8被触发到低电平后模块向外发射数据，只是基本通信功能的实现，不存在地址码与通信协议。


### 采用串口1与PC通信
- 2月27日 调通串口1的任意数据长度接收
- 2月27日 调通串口1的DMA发送
- 2月27日 首次完成串口透传（没有地址）

### SI4432电气连接信息
```
GND------------>GND
SDN------------>PB11
NIRQ----------->PB10
NSEL----------->PB12
SCLK----------->PB13(SPI2)
SDI------------>PB15(SPI2)
SDO------------>PB14(SPI2)
VCC------------>VCC3.3(1.8~3.6v)

```

### OLED接线信息

```
GND------------>GND
VCC------------>VCC3.3
D0(SCLK) ------>PB0
D1(SDIN) ------>PB1
RST------------>PB14
DC------------->PC8
CS------------->PC9
```

### 注意:

STM32F103C8/RB/RC等低端芯片均建议采用此模板进行软件开发

 
## 许可

[MIT](./LICENSE) &copy; [havenxie](http://github.com/havenxie)
