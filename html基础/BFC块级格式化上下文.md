# 块格式化上下文

## 块格式化上下文(Block Formatting Context,BFC)是 Web 页面的可视 CSS 渲染的一部分，是块盒子的布局过程发生的区域，也是浮动元素与其他元素交互的区域

## 创建 BFC 的具体方式

- float 属性不为 none
- position 为 absolute 或者 fixed
- display 为 inline-block，table-cell，flex
- overflow 为 hidden、auto、scroll

## BFC 能解决什么问题

- 1,边距重叠问题
- 2,盒子塌陷问题
- 3,清楚浮动问题
- 4,环绕文字问题

### 1,边距重叠问题(将 bottom 包在 p 标签里，p 标签样式为 overfl:hidden)

```javascript
    <style>
        *{
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        div{
            width: 100px;
            height: 100px;
            background-color: blueviolet;
        }
        p{
            overflow: hidden;
        }
        .top{
            margin-bottom: 20px;
        }
        .bottom{
            margin-top: 10px;
        }
    </style>
<body>
    <div class="top"></div>
    <p>
        <div class="bottom"></div>
    </p>
</body>
```

### 2,盒子塌陷问题(当子盒子想要距离父盒子一定距离时，将父盒子样式设置为 overflow: hidden 才会有效，不然整个家族都移动了)

```javascript
    <style>
        *{
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        .parent{
            width: 200px;
            height: 200px;
            background-color: blueviolet;
            overflow: hidden;
        }
        .son{
            width: 100px;
            height: 100px;
            background-color: crimson;
            margin-top: 20px;
        }

    </style>
<body>
    <div class="parent">
        <div class="son"></div>
    </div>
</body>
```

### 3,清楚浮动问题

```javascript
<style>
        *{
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        .son{
            width: 100px;
            height: 100px;
            background-color: crimson;
            float: left;
        }
        .box{
            width: 200px;
            height: 200px;
            background-color: cyan;
        }
        .parent{
            overflow: hidden;
        }
    </style>
<body>
    <div class="parent">
        <div class="son"></div>
        <div class="son"></div>
    </div>
    <div class="box"></div>
</body>
```

### 4,环绕文字问题(有时我们不需要文字环绕着图片，就可以将其设置为 BFC)

```javascript
 <style>
        *{
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        .box{
            width: 100px;
            height: 100px;
            background-color: darkorchid;
            float: left;
        }
        .parent{
            width: 200px;
        }
        .text{
            overflow: hidden;
        }
    </style>
<body>
    <div class="parent">
        <div class="box"></div>
        <div class="text">人生在世，每个人都应该拥有一个梦想，拥有一个实现的目标，拥有一个前进的方向。人生就是一个拥有梦想，追求梦想，实现梦想的过程。 正值青春的我们拥有春天的朝气，拥有夏天的热烈，拥有秋天的成熟，拥有冬天的坚强。</div>
    </div>
</body>
```
