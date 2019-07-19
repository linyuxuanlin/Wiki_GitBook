# HTML 学习笔记

## 基本架构

```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>标题</title>
</head>
<body>
    
</body>
</html>
```

可直接在编辑器输入 `html:5` 调出

## 语句

一些规范：

1. 标签使用小写，元素必须闭合
2. 在开始标签中添加斜杠以关闭空元素  eg. `<br />`
3. 避免使用标记语言的特性，以便所有样式都存放于 CSS 中

### 标题

用 ~ 标签定义

```markup
<h1>这是一个标题</h1>
```

### 段落

```markup
<p>这是一个段落</p>
```

### 链接

```markup
<a href="url">链接显示的文本</a>
```

### 图像

```markup
<img src="/xx.png" width="258" height="39" />
<a href="url"><img src="/xx.png" width="258" height="39"></a>
```

### 换行

不产生新段落换行：

```markup
<br />
```

### 分割线

```markup
<hr>
```

### 注释

```markup
<!注释>
<!-- 注释 -->
```

### 文本格式化

```markup
<b>粗体</b>
<i>斜体</i>
<del>删除</del>
<q>块引用</q>
```

### 列表

```markup
<!无序>
<ul>
    <li>第一项</li>
    <li>第二项</li>
</ul>

<!有序>
<ol>
    <li>第一项</li>    
</ol>
```

### 表格

```text
<table>
  <thead>
    <tr><th > 时间 </th><th > 地点 </th></tr>
  </thead>
  <tbody>
    <tr><td>2000</td><td > 悉尼 </td></tr>
    <tr><td>2004</td><td > 雅典 </td></tr>
    <tr><td>2000</td><td > 北京 </td></tr>
  </tbody>
</table>
```

## 参考与致谢

* [HTML 教程 \| 菜鸟教程](http://www.runoob.com/html/html-tutorial.html)
* [HTML 30 分钟入门教程](http://deerchao.net/tutorials/html/html.htm)

