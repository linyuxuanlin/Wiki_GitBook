# Altium Designer 系列教程（二）：基础知识

## 安装库文件

Altium Designer 的库相当于把每个分立元件（如电阻、电容等）的原理图/PCB/3D模型封装起来，需要的时候直接拿来用。如果不想每个元件都自己画，可以直接用厂商提供的库。

### **推荐比较齐全的库**

* **JLCSMT\_LIB**：嘉立创提供的标准集成库，包含嘉立创可以 SMT 贴片的所有元件，直接用这个集成库，打板/SMT 的时候兼容性会比较好；
* **Miscellaneous Devices**（内置）：自带的元器件集成库，比较全但打板时兼容性一般；
* **Miscellaneous Connectors**（内置）：自带的接插件集成库；
* **Hare\_Library**：彬哥自己画的原理图库和封装库，涵盖队内硬件所需的大部分元器件；

以上库文件已共享至 [**我的坚果云**](https://www.jianguoyun.com/p/DX2d84cQ-OOjBxj0kPwB) ，请自行下载。

### **不常见的元器件**

对于一些不常见的元器件，可以上 [**SnapEDA**](https://www.snapeda.com/) ****查找，基本上都可以找到。

### **安装库的方法**

1. 将库文件全部 **拷贝** 至软件对应的 **Shared\Library** 文件夹下；
2. 打开 Altium Designer ，在右侧面板点击 **Components** 页面，点击右上角 **三条杠** 标志，点击 **File-based Library Preferences** 选项，点击 **已安装** 页面，点击 **安装** 按钮，安装对应的库文件；
3. 几种特殊情况：
   * 嘉立创集成库的路径位于 **JLCSMT\_LIB\Project Outputs for Miscellaneous Devices LC** 文件夹内；
   * 若第三方库文件非 **集成库（.IntLib）**，而是 **原理图库（SchLib）** 或 **封装库（PcbLib）** 的形式，则需 **同时安装** 以上两个文件。此时需要在安装库文件时弹出的路径选择窗口右侧点击下拉框切换 **All Files\(\*.\*\)** 通配符，否则只能看到 **.Intlib** 格式的文件。
   * 从 **SnapEDA** 下载的元器件：
     1. 先在 **Shared\Library** 路径下创建 **SnapEDA** 文件夹（便于后期整理）；
     2. 将下载的 **.lia** 文件解压并拷贝至 **SnapEDA** 文件夹内；
     3. 将 **SnapEDA** 文件夹内的 **.lia** 文件 **直接拖进** Altium Designer **左侧** **Projects** 面板，自动弹出 **P-CAD 导入向导** 页面，一直点 **Next** ，直到看见 **Current Layer Mappings** 页面，执行以下操作：
        * 将 **Layer '10'** 右键选择为 **Mechanical Layer 1** ；
        * 将 **Layer '20'** 右键选择为 **Mechanical Layer 13** ；
        * 将 **Layer '21'** 右键选择为 **Mechanical Layer 15** ；
     4. 一直点 **Next** 直至完成。



## 快捷键操作

于 Altium Designer 而言，熟练掌握常用的快捷键，可以很大程度提高效率。Altium Designer 的系统快捷键都是根据菜单下命令中有下划线的字母组合而成，例如 **Place-Line** 的快捷键为 **P-L** （先按 P 再按 L）

### 原理图

* 显示 Library 面板：**PP**
* 复制元件并自动更新位号：**按住 Shift + 拖动**
* 元件自动编号：**TAA**
  * Reset All：复位所有元件标号，使其变成 " 字母 + ? " 的格式
  * Update Change List：对元件列表进行标号变更
  * Accept Changes（Create ECO）：表示接受编号变更，实现原理图的变更
* 生成 BOM 表：**RI**
* 更新 PCB：**DU**
* 左对齐（右）：**AL**（**AR**）

### PCB

* 把原理图的变更导入 PCB：**DI**
* 把 PCB 的变更覆盖回原理图：**DU**
* 切换单位（英寸/毫米）：**Q**
* 旋转元器件（任意角度）：**EMO**
* 把元件放置在底层：**拖动同时按 L**
* 自动布局：**框选 + TOL**
* 设置坐标原点：**EOS**
* 设置栅格：**G**
* 自动布线：**UAA**
* 清除布线：**UUA**
* 高亮接线：**按住 Shift + 光标移至线**
* 高亮节点所对应连线：**按住 Ctrl + 左键单击**
* 水平翻转：**Ctrl + F**
* 测量：**Ctrl + M**
* 切换视图（二维 / 三维）：**2 / 3**
* 三维视图中旋转：**按住 Shift + 拖动**
* 清除过滤器：**Shift + C**
* 切换单层/多层显示：**Shift + S**
* 过孔盖油（可略，打板时可直接选择）
  1. 单击某一过孔
  2. 右键 - 查找相似对象
  3. 选择大小属性为 Same，确定以激活选择所有过孔
  4. 在属性中的 Solder Mask Expansion 中把顶层和底层都勾选上
* 设置自动布线规则
  1. **UAA**
  2. 新建策略并编辑规则
  3. 一般修改 Routing 中的规则（新建规则）
     * Width：设置线的粗细
     * Routing Via Style ：设置过孔规则

### 原理图库

### 封装库

* 测量距离：**Ctrl + N**
* 切换单位（英寸/毫米）：**Q**

