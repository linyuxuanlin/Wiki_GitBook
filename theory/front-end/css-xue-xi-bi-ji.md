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

## 各类属性及可选值

### 颜色

```css
/*字体颜色*/
color: #56a455;

/*背景色*/
background-color: blue;
```

### 透明度

取值 0.0 ~ 1.0

```css
/*透明度*/
opacity: 0.5;
```

### 字体大小

| 样式 | 百分比 | EM 值 |
| :--- | :--- | :--- |
| h1 | 200% | 2em |
| h2 | 150% | 1.5em |
| h3 | 133% | 1.125em |
| body | 100% | 1em |

```css
/*字体大小*/
font-size: 200%;
```

### 字体选用

```css






/*字体选用*/


/*多单词组成的字体名称，要放引号里*/


/*本地*/

font-family: 'Courier New',
Courier,
monospace,
外链字体名称;

/*外链*/

@font-face {
    font-family: 外链字体名称;
    src: url('外链地址');
}


/*文本格式化，默认值为 normal*/


/*粗体*/

font-weight: bold;

/*斜体*/

font-style: italic;

/*大小写*/


/*uppercase，lowercase，capitalize（首字母大写）*/

text-transform: uppercase;

/*下划线*/

text-decoration: underline;

/*删除线*/

text-decoration: line-through;

/*行间距*/

line-height: 1.4em;

/*对齐*/


/*left,right,center,justify（两端对齐）*/

text-align: left;

/*链接样式*/


/*:link,:visited*/

a:link {
    ...
}


/*:hover,:active,:focus 待补充*/
```



## 参考与致谢

* [CSS 入门教程](https://developer.mozilla.org/zh-CN/docs/Web/Guide/CSS/Getting_started)
* [CSS3 Tutorial 《CSS3 教程》](https://waylau.gitbooks.io/css3-tutorial/content/)



