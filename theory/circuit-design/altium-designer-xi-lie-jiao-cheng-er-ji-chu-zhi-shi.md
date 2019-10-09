# Altium Designer 系列教程（二）：基础知识

## 安装库文件

Altium Designer 的库相当于把每个分立元件（如电阻、电容等）的原理图/PCB/3D模型封装起来，需要的时候直接拿来用。如果不想每个元件都自己画，可以直接用厂商提供的库。

**几个种类比较齐全的库：**

* JLCSMT\_LIB：嘉立创提供的标准集成库，包含嘉立创可以 SMT 贴片的所有元件，直接用这个集成库，打板/SMT 的时候兼容性会比较好；
* Miscellaneous Devices（内置）：自带的元器件集成库，比较全但打板时兼容性一般；
* Miscellaneous Connectors（内置）：自带的接插件集成库；
* Hare\_Library：彬哥自己画的原理图库和封装库，涵盖队内硬件所需的大部分元器件；

以上库文件已共享至 [**我的坚果云**](https://www.jianguoyun.com/p/DX2d84cQ-OOjBxj0kPwB) ，请自行下载。

**不常见的元器件：**

对于一些不常见的元器件，可以上 [**SnapEDA**](https://www.snapeda.com/) ****查找，基本上都可以找到。

**安装库的方法：**

1. 将库文件全部 **拷贝** 至软件对应的 **Shared\Library** 文件夹下；
2. 打开 Altium Designer ，在右侧面板点击 **Components** 页面，点击右上角 **三条杠** 标志，点击 **File-based Library Preferences** 选项，点击 **已安装** 页面，点击 **安装** 按钮，安装对应的库文件；
3. 几种特殊情况：
   * 嘉立创集成库的路径位于 **JLCSMT\_LIB\Project Outputs for Miscellaneous Devices LC** 文件夹内；
   * 若第三方库文件非 **集成库（.IntLib）**，而是 **原理图库（SchLib）** 或 **封装库（PcbLib）** 的形式，则需 **同时安装** 以上两个文件。此时需要在安装库文件时弹出的路径选择窗口右侧点击下拉框切换 **All Files\(\*.\*\)** 通配符，否则只能看到 **.Intlib** 格式的文件。



## 快捷键操作

于 Altium Designer 而言，熟练掌握常用的快捷键，可以很大程度提高效率。Altium Designer 的系统快捷键都是根据菜单下命令中有下划线的字母组合而成，例如 **Place-Line** 的快捷键为 **P-L** （先按 P 再按 L）



