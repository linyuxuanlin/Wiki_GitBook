# JavaScript 学习笔记

## 调用外部 JS

```markup
<!DOCTYPE html>
<html>
    <head>
        <script src="xx1.js"></script>
    </head>
    <body>
        <script src="xx2.js"></script>
    </body>
</html>
```

## 输出

### 弹出警告框

```javascript
window.alert("Hello");
```

### 操作 HTML 元素

```markup
<!DOCTYPE html>
<html>
    <body>
        <h1> 我的第一个 Web 页面 </h1>
        <p id="demo"> 我的第一个段落 </p>
        <script>
            document.getElementById ("demo").innerHTML = "段落已修改。";
        </script>
    </body>
</html>
```



