# CSS隐藏元素的方法
## 使用CSS隐藏元素的方法有：display:none;、opacity:0;、visibility:hidden;、position:absulate;overflow:hidden;、clip-path:polygon(0 0, 0 0, 0 0, 0 0);、height:0;overflow:hidden;

## display:none
### none就是把元素在页面不显示，使用这个属性，被隐藏的元素不会占据任何空间，用户交互操作例如点击事件都不会生效，读屏软件也不会读到元素的内容，这个元素的任何子元素也会同时被隐藏。当使用该属性将元素从显示状态切换为隐藏状态时，元素不占据原本的空间，会触发浏览器的重绘与回流。为这个属性添加过渡动画是无效的，他的任何不同状态值之间的切换总是会立即生效。这种方式产生的效果就像元素完全不存在，但在DOM中依然可以访问到这个元素，也可以通过DOM来操作它。
```javascript
    <style type="text/css">
        #box{
            width: 200px;
            height: 200px;
            border: 1px solid red;
        }
        .display-hide{
            display: none;
        }
    </style>
 <div id="box"></div>
    <script type="text/javascript">
        document.getElementById("box").addEventListener("click",e=>{
            alert("第一次点击之后就会被隐藏，后续再无法点击");
            console.log(e)
            console.log(e.srcElement)
            console.log(e.srcElement.classList)
            console.log(e.srcElement.classList.add)
            e.srcElement.classList.add("display-hide");
        })
    </script>
```