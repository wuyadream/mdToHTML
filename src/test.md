> 这个系列的笔记只是为了记录最近工作中学习和用到的知识，方便以后自己查看，所以排版和格式的可能不会很漂亮。

### 1、scrollTop

语法：`$(selector).scrollTop(offset)`

作用：返回或设置匹配元素的滚动条的垂直位置。


### 2、'margin:0 auto'失效
大部分时间是因为没有设置宽度。

### 3、媒体查询的使用
例子：在页面宽度小于560px时隐藏div块。

使用：
```
@media only screen and (max-width:560px) {
div { display:none;}
}
```
### 4、绝对定位 'position:absolute'
绝对定位的元素会从文档流中脱离，并相对于其包含块进行定位。

包含块由最近的`position`属性为`relative`、`fixed`、`absolute`的祖先元素所决定的。

如果不存在这样的包含块，则其包含块为初始包含块。

根元素所在的包含块为初始包含块，对于连续媒体，初始包含块是视口大小的矩形。


### 5、绝对定位的使用
-  图标定位
  
  采用无依赖的绝对定位，设置图标为绝对定位，再根据margin值去调整。
  
-  伸展容器
  
  设置绝对定位+`top=0,left=0,right=0,bottom=0`。
  
-  水平垂直居中
 
  当尺寸限制、拉伸与`margin : auto`同时出现时，就能实现绝对居中效果。(炒鸡好用的...)
  
```
div {
    position:absolute;
    left:0;
    right:0;
    top:0;
    bottom:0;
    width:50%;
    height:50%;
    margin:auto;
}
```
### 6、相对定位和绝对定位
相对定位是元素相对于元素本身原来的位置进行偏移；

绝对定位是元素相对于最近的非static定位的父元素位置进行偏移。


### 7、div滚动到顶部时固定在顶部效果
```
    $(window).scroll(function () {
        if($(window).scrollTop>=900) {
            $('#nav_div').addClass('fix_div');
        } else {
            $('#nav_div').removeClass('fix_div');
        }
    })
```
### 8、预检请求
浏览器为了保证发送的请求能成功被响应会发送两次请求，第一次请求是使用OPTIONS方法发起一个预检请求到服务器，以获知服务器是否允许该实际请求。

### 9、设置placeholder字体颜色
```
 ::-webkit-input-placeholder { color:#dcdcdc; }
 ::-moz-placeholder { color:#dcdcdc; } /* firefox 19+ */
:-ms-input-placeholder { color:#dcdcdc; } /* ie */
 input:-moz-placeholder { color:#dcdcdc; }
```