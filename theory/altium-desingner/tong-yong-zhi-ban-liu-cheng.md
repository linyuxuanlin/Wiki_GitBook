---
description: Altium Designer 制版流程（基于 AD19）
---

# 通用制版流程

## 新建项目

* 项目内创建原理图和 PCB 文件
* （原理图库和封装库）

## 原理图库

## 封装库

* 测量详细参数（距离） Ctrl + N
* 按 Q 换毫米单位

## 画原理图

* 直接执行菜单命令Place-Part（PP），也能调用出 Library 面板
* 元件属性
  * Designator：元件位号，是元件的唯一标识，用来标识原理图中的不同的元件
    * U：一般用于标识IC类
    * R：电阻类
    * C：电容类
    * J：接口类
    * X：晶振
    * D：二极管
    * Q 或 T：三极管
  * Comment：元件大小参数，如电阻的阻值、电容的容值、IC芯片型号等
  * Description：用于填写元件的功能描述
* 按住 Shift 拖动元件，可以复制并自动更新元件位号
* 元件自动编号（TAA）
  * Reset All 可以复位所有元件标号，使其变成”字母+?”的格式
  * Update Change List 按钮可以对元件列表进行标号变更
  * Accept Changes（Create ECO）表示接受编号变更，实现原理图的变更
* 生成 BOM 表（元件物料清单）
  * Reports-Bill of Materials（Ri）

## 画 PCB

* 编译（CC）
* 更新 PCB
  * 从原理图导入变更至 PCB（DI）
  * 从 PCB 更新原理图（DU）
* 放置元件
  * 置于底层
    * 拖动同时按 L
  * 自动布局
    * 选中需要处理的元件
    * TOL
  * 设置坐标原点（EOS）
* 布线
  * 自动布线（UAA）（不推荐？）
  * 清除所有布线（UUA）
  * Ctrl + 单击 ： 高亮
  * 顶层（元件所在面）&底层
  * 过孔（穿透顶层&底层）
    * 设置网络属性（所接的端口）
* 画板子形状（DSD）
  * 最外层要设置成 机械层1
  * 边框圆角：4 mm
  * 给铜柱的孔：里 3.1 mm ; 外 5 mm
* 版权信息
  * 字体放在丝印层（顶层/底层，放底层要镜像）
* 敷铜
  * 放置多边形平面
    * 顶层&底层都要
* 实用方法
  * 测量：Ctrl + M
  * 按 3 切换 3D 模式，按紧 Shift 拖动鼠标旋转视角 

## 杂项

* snapEDA 找元件库+封装库
  * [https://www.snapeda.com/about/import/](https://www.snapeda.com/about/import/)
  * 拖 .lia 文件进 Altium.，一直点 next;
  * 中间某一步填写：
    * For Layer '10', choose: Mechanical Layer 1
    * For Layer '20', choose: Mechanical Layer 13
    * For Layer '21', choose: Mechanical Layer 15
* 布局时尽量从大的元件下手，因为大的元件对空间要求高，且大的元件通常有较多的引脚

## 参考与致谢

* [AD 原理图绘制](https://seujxh.wordpress.com/2018/01/02/ad原理图绘制/)
* [Altium Designer 18.0.7 Beta 系列教程（2） 基础PCB布局布线](https://seujxh.wordpress.com/2017/12/07/altium-designer-18-0-7-beta-系列教程（2）-基础pcb布局布线/)
* [Logo 添加](https://seujxh.wordpress.com/2018/10/03/logo添加/)

