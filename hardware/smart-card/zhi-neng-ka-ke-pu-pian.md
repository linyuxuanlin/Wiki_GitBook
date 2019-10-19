---
description: 免责声明：本文涉及的技术仅供安全学习和教学用途，禁止非法使用！
---

# 智能卡-科普篇

## NFC 协议

> NFC 是现在主流的非接触式 IC 卡的读卡技术，其全称是近场通信（near field communication），是基于无线射频识别 RFID（Radio Frequency Identification）技术发展起来的一种近距离无线通信技术，与 RFID 一样，NFC 也是通过频谱中无线频率部分的电磁感应耦合方式传递，但两者之间还是存在很大的区别。NFC 的传输范围比 RFID 小，RFID 的传输范围可以达到 0~1m，但由于 NFC 采取了独特的信号衰减技术，相对于 RFID 来说 NFC 具有成本低、带宽高、能耗低等特点。

NFC 技术主要特征如下：

1. 用于近距离 \(10cm 以内\) 安全通信的无线通信技术。
2. 射频频率：13.56MHz
3. 射频兼容：ISO 14443，ISO 15693，Felica 标准。
4. 数据传输速度：106kbit/s，212 kbit/s，424kbit/s
5. 现在手机都包含 NFC 功能，其主板上嵌入了 NFC 模块，具有三种功能模式：NFC 手机作为识读设备 \(读写器\)、NFC 手机作为被读设备 \(卡模拟\)、NFC 手机之间的点对点通信应用。

## 卡的种类

* **ID**：身份识别卡（Identification Card）。**不可写入**，有固定编号。
  * EM4XX（ID 卡）：低频卡，
  * T5577（可修改 ID 卡）：低频卡，
  * HID Prox II（简称 HID）：低频卡，
* **IC**：集成电路卡（Integrated Circuit Card），又称智能卡（Smart Card）。可**加密读写**，容量大。用于一卡通等消费系统。主要有 Mifare 系列等。
  * **Mifare S50（M1）**：高频卡，最常见，出厂固化 UID（每张卡独一无二），可储存修改数据。用于学生卡，饭卡，公交卡，门禁卡等。
  * **Mifare UltraLight（M0）**：高频卡，低成本，出厂固化 UID，可储存修改数据。
  * **Mifare UID Chinese Magic Card（UID）：**高频卡，中国魔术卡，M1 变异版本，可修改 UID，可完整克隆 M1卡的数据；但现在有读卡系统可检测，屏蔽复制卡。
    * **FUID**：UID 只能修改一次，防屏蔽。
    * **CUID**：FUID 优化版，支持 UID 重复擦写，无需锁卡，自动起防屏蔽作用。
  * **CPU**：CPU 卡由 CPU 部分（7K 容量）及 M1 部分（1K 容量）组成，可以读出其中的 M1 部分，CPU 部分目前无解。读出 M1 部分后，可将数据转写至 UID 卡使用

## 卡的数据

以 M1 卡为例，容量为 1KB，分 16 个扇区，每扇区分 4 个数据块，每个数据块 16 字节。

数据块按 0 ~ 3 编号，前 3 个块储存信息，最后一个储存密码，按顺序含 KEYA（密钥 A）、控制位、KEYB（密钥 B），每个扇区可通过它所包含的密钥 A / B 单独加密。

0 扇区 0 块比较特殊，存放着制造商代码（包括芯片序列号 UID，ATQA 和 SAK），不可修改，只能读。

**非加密卡**：所有扇区的 KEYA 和 KEYB 都是默认值 FFFFFFFFFFFF .  
**加密卡**：其中有扇区的 KEYA 和 KEYB 不是 FFFFFFFFFFFF，部分扇区加密称半加密卡，所有扇区都加密称全加密卡。

各种卡的特征（返回的信息）：

* M1 S50：TYPE : NXP MIFARE CLASSIC 1k \| Plus 2k SL1
* UID：Answers to chinese magic backdoor commands: YES
* CPU：ATQA : 00 04；SAK : 28 \[1\]；TYPE : JCOP31 or JCOP41 v2.3.1

## 安全性测试

### 步骤

* 判断是 ID 还是 IC （如果是 ID 会印在卡上）
* ID 卡
  * 读卡片 ID 号
  * 将 ID 号写进 T5577 卡
* IC 卡
  * 获得任意扇区的密匙（以下任意一种即可）
    1. PRNG漏洞攻击得 0 扇区密匙
    2. 默认密码扫描获得密匙
    3. 嗅探读卡机和卡片交互数据获得密匙
    4. 模拟成 M1 卡刷卡后捕获密匙（挑读卡机，兼容性不好）
  * 利用 MFOC 漏洞，用已知扇区密匙求所有扇区密匙
  * 将数据写入 UID 卡

### M1 原理

跳转 [轻松理解 M1 卡的结构](https://pm3.echo.cool/index.php/2019/04/29/%e8%bd%bb%e6%9d%be%e7%90%86%e8%a7%a3m1%e5%8d%a1%e7%9a%84%e7%bb%93%e6%9e%84/) 。

## 写在后面

> 只要有助于改进现状、探索未知，人们就应该被允许自由地使用各种工具和信息。 —— 《黑客与画家》

## 参考与致谢

* [手把手教 如何模拟 IC 加密卡](https://zhuanlan.zhihu.com/p/81384126)
* [CPU 模拟卡简单介绍](https://pm3.echo.cool/index.php/2019/03/23/cpu%e6%a8%a1%e6%8b%9f%e5%8d%a1%e7%ae%80%e5%8d%95%e4%bb%8b%e7%bb%8d/)
* [Proxmark 实验室](https://pm3.echo.cool/)
* [轻松理解 M1 卡的结构](https://pm3.echo.cool/index.php/2019/04/29/%e8%bd%bb%e6%9d%be%e7%90%86%e8%a7%a3m1%e5%8d%a1%e7%9a%84%e7%bb%93%e6%9e%84/)
* [一篇文章讲清楚 ID，IC，M1，CPU 卡的区别](https://pm3.echo.cool/index.php/2019/04/29/%e4%b8%80%e7%af%87%e6%96%87%e7%ab%a0%e8%ae%b2%e6%b8%85%e6%a5%9aid%ef%bc%8cic%ef%bc%8cm1%ef%bc%8ccpu%e5%8d%a1%e7%9a%84%e5%8c%ba%e5%88%ab/)


