## 流
**“流”又叫文档流，是css的一种基本定位和布局机制。** 流是html的一种抽象概念，暗喻这种排列布局方式好像水流一样自然自动。“流体布局”是html默认的布局机制，如你写的html不用css，默认自上而下（块级元素如div）从左到右（内联元素如span）堆砌的布局方式。

## 块级元素和内联元素

块级元素是指单独撑满一行的元素，如==div、ul、li、table、p、h1==等元素。这些元素的display值默认是block、table、list-item等。

内联元素又叫行内元素，指只占据它对应标签的边框所包含的空间的元素，这些元素如果父元素宽度足够则并排在一行显示的，如==span、a、em、i、img、td==等。这些元素的display值默认是inline、inline-block、inline-table、table-cell等。


实际开发中，我们经常把display计算值为inline inline-block inline-table table-cell的元素叫做内联元素，而把display计算值为block的元素叫做块级元素。

## width: auto 和 height: auto

width、height的默认值都是auto。

对于块级元素，流体布局之下width: auto自适应撑满父元素宽度。这里的撑满并不同于width: 100%的固定宽度，而是像水一样能够根据margin不同而自适应父元素的宽度。

对于内联元素，width: auto则呈现出包裹性，即由子元素的宽度决定。

无论内联元素还是块级元素，height: auto都是呈现包裹性，即高度由子级元素撑开。

注意父元素height: auto会导致子元素height: 100%百分比失效。

css的属性非常有意思，正常流下，如果块级元素的width是个固定值，margin是auto，则margin会撑满剩下的空间；如果margin是固定值，width是auto，则width会撑满剩下的空间。这就是流体布局的根本所在。