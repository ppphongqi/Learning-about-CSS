### 1.解决inline-block元素设置overflow:hidden属性导致相邻行内元素向下偏移

```
.wrap {
  display: inline-block;
  overflow: hidden
	vertical-align: bottom
}
```

### 2.超出部分显示省略号

```
// 单行文本
.wrap {
	overflow:hidden;/*超出部分隐藏*/
	text-overflow:ellipsis;/*超出部分显示省略号*/
	white-space:nowrap;/*规定段落中的文本不进行换行 */
}
// 多行文本
.wrap {
    width: 100%;
    overflow: hidden;
    display: -webkit-box;   //将对象作为弹性伸缩盒子模型显示  *必须结合的属性*
    -webkit-box-orient: vertical;   //设置伸缩盒对象的子元素的排列方式  *必须结合的属性*
    -webkit-line-clamp: 3;   //用来限制在一个块元素中显示的文本的行数
    word-break: break-all;   //让浏览器实现在任意位置的换行 *break-all为允许在单词内换行*
}

```

### 3.css是心啊不换行、自动换行、强制换行

```
//不换行
.wrap {
  white-space:nowrap;
}
//自动换行
.wrap {
  word-wrap: break-word;
  word-break: normal;
}
//强制换行
.wrap {
  word-break:break-all;
}

```

### 4.css实现文本两端对齐

```
.wrap {
    text-align: justify;
    text-justify: distribute-all-lines;  //ie6-8
    text-align-last: justify;  //一个块或行的最后一行对齐方式
    -moz-text-align-last: justify;
    -webkit-text-align-last: justify;
}

```

### 5.实现文字竖向排版

```
.wrap {
    width: 25px;
    line-height: 18px;
    height: auto;
    font-size: 12px;
    padding: 8px 5px;
    word-wrap: break-word;/*英文的时候需要加上这句，自动换行*/  
}
// 多列展示时
.wrap {
    height: 210px;
    line-height: 30px;
    text-align: justify;
    writing-mode: vertical-lr;  //从左向右    
    writing-mode: tb-lr;        //IE从左向右
    //writing-mode: vertical-rl;  -- 从右向左
    //writing-mode: tb-rl;        -- 从右向左
}

```

### 6.使元素鼠标事件失效

```
.wrap{
    //如果按tab能选中该元素，如button，然后按回车还是能执行对应的事件。如click。
    pointer-events:none;
    cursor:default;
}
```

### 7.禁止用户选择

```
.wrap {
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}

```

### 8.cursor属性

```
.wrap{
    cursor:pointer;
    cursor:help;
    cursor:wait;
    cursor:move;
    cursor:crosshair;
}
```

### 9.使用硬件加速

```
.wrap{
    stransform:translateZ(0)
}
```