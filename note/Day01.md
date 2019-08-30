# CSS3 弹性布局

## 前言

- 弹性布局适用于较简单的场景
- 过于复杂的场景可以尝试着使用CSS3的Grid布局
- 弹性布局在PC端中还存在兼容性问题，移动端中无兼容性问题

### 1.容器属性
 css3为新增的弹性布局提供了多个属性，分别为弹性盒模型的容器属性，以及弹性盒子中子元素的子元素属性。
#### 1.1 display

```
display:flex;           /*将容器声明为一个弹性盒模型且容器表现为块级元素*/
display:inline-flex;    /*将容器声明为一个弹性盒模型且容器表现为行内元素*/
```
#### 1.2 flex-direction(主轴方向)
> flex-direction可以设置主轴的方向，默认值为row。


```
flex-direction：row | row-reverse | column | column-reverse
```
- row:默认
- row-reverse:主轴反转
- column:垂直轴排列(像block一样)
- column:垂直反转

#### 1.3 flex-wrap(子元素换行)
> flex-wrap就是控制弹性盒模型的子元素换行方式的，默认值为nowrap。

```
flex-wrap：nowrap | wrap | wrap-reverse
```
- flex-wrap：nowrap; /*不换行，等比例缩小*/
- flex-wrap：wrap; /*自动换行*/
- flex-wrap：wrap-reverse; /*自动反方向换行，往下换行变成往上换行*/

#### 1.4 justify-content(主轴对齐)
> justify-content控制主轴的对齐方式，默认向主轴开始起点位置对齐，值为flex-start。


```
justify-content：flex-start | flex-end | center | space-between | space-around
```

- justify-content：flex-start; /*向主轴开始位置对齐*/
- justify-content：flex-end; /*向主轴结束位置对齐*/
- justify-content：center; /*主轴居中对齐*/
- justify-content：space-between; /*等间距对齐，两端不留空*/
- justify-content：space-around; /*等间距对齐，两端留空，每个元素左间距与右间距大小相等*/


#### 1.5 align-items(垂直轴的对齐方式)
> align-items控制垂直轴的对齐方式，默认向主轴开始起点位置对齐，值为flex-start。

```
align-items：flex-start | flex-end | center | baseline | stretch
```
- align-items：flex-start; /*向垂直轴开始位置对齐*/
- align-items：flex-end; /*向垂直轴结束位置对齐*/
- align-items：center; /*垂直轴居中对齐*/
- align-items：baseline; /*文本基线对齐，用的不多*/
- align-items：stretch;    /*垂直轴方向上的height/width若值为auto，则自动填满，但依然受到min/max-width/height的控制。不设置弹性盒模型时，height默认值为内容区大小，若设置为弹性盒模型且align-items设置为stretch，则高度占满整个父容器*/
> 个人觉得就是justify-content的方式逆时针转了90度，从横向变为了纵向

### 2. 子元素属性

#### 2.1 order

>order属性可用于设置子元素的位置，order的值越小排在越前面，默认值为0，可以设置负值。

例：
```
.box-item3 {
	background: green;
	order:-1;
}
/*在其他子元素不设置order的情况下item3将会排在第一个 */

```
##### 总结:通过为每一个子元素设置order值可以使得布局不依赖于html的结构。
