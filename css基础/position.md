# position定位
## css中position是比较常见的定位，position的取值有 static、relative、absulate、fixed、sticky、inherit

## static
### 这种情况下元素使用正常的布局，即元素在文档常规流中当前的布局位置。此时top、right、left、bottom和z-indexz-index属性无效

## relative 相对定位
### 这种情况下，元素先放在未添加定位时的位置，再在不改变页面布局的前提下调整元素的位置所以会在此元素为添加定位时所在位置留下空白，相对定位元素经常被用来作为绝对定位元素的容器块。position:relative 对 table-*-group, table-row, table-column, table-cell, table-caption 元素无效。

## absolute 绝对定位
### 元素的位置相对于最近的已定位父元素，如果元素没有已定位的父元素，那么它的位置相对于<html>，通常的使用方案是在外层嵌套一层relative相对定位元素作为父元素，再设置绝对定位元素的偏移将会相对于外层的relative元素进行偏移，绝对定位完全脱离文档流与文本流，不占据文档空间，对于top、bottom、left、right、z-index属性的设置有效。

## fixed 固定定位
### 元素的位置相对于浏览器窗口是固定的，即使是窗口滚动了元素也不会移动。

## sticky 粘性定位
### 元素的位置是基于用户的滚动位置来定位，粘性定位的元素是依赖用户的滚动，在position: relative与position: fixed定位之间切换，在页面显示时sticky的表现类似于position: relative，而当页面滚动超出目标区域时sticky的表现类似于position: fixed，它会固定在目标位置，元素定位表现为在跨越特定阈值前为相对定位，之后为固定定位，这个特定阈值指的是top、right、bottom、left其中之一，必须通过指定top、right、bottom、left四个阈值其中之一，才可使粘性定位生效，否则其行为与相对定位相同。

