# ZenDriver - 电机驱动

## 成品

图片待补充……

## 用户手册

### 特性

* 超宽电源电压输入，兼容 7.2 ～ 24V 电源输入；融合防反接功能，避免电源接反烧坏驱动器；
* 正常工作电流 6A 持续输出，峰值达 70A ；
* 兼容主流控制器：STM32，树莓派，Arduino，51，AVR，Freescale 等，设置对应控制频率即可驱动电机；
* 双路电机驱动，每路电机由两路 PWM 控制转速与方向，简化了接线；
* 提供电池转接端口（拓展给另一个驱动板）；
* 集成 LM317 稳压为芯片供电，可稳定输出 5V 电压，用于其他设备供电；
* 提供电机免转接端口（包括编码器信号与供电口）。

### 参数

* 尺寸：45 mm x 53 mm
* 输出电流：6A 持续输出，峰值 70A
* 输入电压：7.2 ~ 24 V
* 控制信号电压：3.3 ~ 5.5 V
* 输入频率：0 ~ 25 kHz
* 推荐控制频率：3 ~ 10 kHz
* 工作温度：- 40 ~ 100 °C
* 额定输出功率：30W（7.2V 供电），120W（12V 供电），140W（24V 供电）
* 保护电路：防反接电路、过流保护

### 引脚说明

![](https://picgo-1253965369.cos.ap-guangzhou.myqcloud.com/UTOOLS1567512965135.png)

* PWR\_OUT：支持 7.2 ~ 24V 电源输入
* PWR\_IN：电源转接口，可转接相同电源给其他设备
* M1\(M2\)：电机接口
* SIG
  * GND：接地
  * 5V\_O：给其他设备提供 5V 电源（不可在此接入 5V 电源）
  * M2B：2 号电机编码器 B 口
  * M2A：2 号电机编码器 A 口
  * M1B：1 号电机编码器 B 口
  * M1A：1 号电机编码器 A 口
  * IN2-（IN2+）：2 号电机 PWM 信号输入
  * IN1-（IN1+）：1 号电机 PWM 信号输入

### 真值表

| IN+ | IN- | 电机 |
| :--- | :--- | :--- |
| + | 0 | 正转 |
| - | 0 | 反转 |
| 0 | + | 反转 |
| 0 | - | 正转 |
| 0 | 0 | 停止 |
| + | + | 停止 |
| - | - | 停止 |

注：+/- 表示正负 PWM 值，PWM 控制频率为 3 ~ 10 kHz.
