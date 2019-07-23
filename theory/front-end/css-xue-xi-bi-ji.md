# CSS 学习笔记

## 调用

在 HTML 的 `<head>` 下添加外部样式表：

```text
<link rel="stylesheet" href="xxx.css">
```

其中，`xxx.css` 为同目录下的 CSS 文件。  
注意：尽量使用 **链接式的外部样式表**（如上）

## 语法

```css
selector{
    prpperty : value;
}
```

## 选择器

| 选择器 | 定义 | 调用 | 优先级 |
| :--- | :--- | :--- | :--- |
| 标签选择器 | p {...} | &lt;p&gt; ... &lt;/p&gt; | 低 |
| 类选择器 | .carrot {...} / p.carrot {...} | class = "carrot" | 中 |
| ID 选择器 | \#first {...} | id = "first" | 高 |

选择器组：用相同样式定义不同元素

```css
h1,h2,h3{
    color : navy;
}
```

## 参考与致谢

* [CSS 入门教程](https://developer.mozilla.org/zh-CN/docs/Web/Guide/CSS/Getting_started)
* [CSS3 Tutorial 《CSS3 教程》](https://waylau.gitbooks.io/css3-tutorial/content/)



