### 前端编码规范

#### 1.规范说明
>此为前端开发团队遵循和约定的代码书写规范，意在提高代码的规范性和可维护性。 
 此规范为参考规范，不全是硬性要求，统一团队编码规范和风格。让所有代码都是有规可循的，并且能够得到沉淀，减少重复劳动。
>
##### 1.1结构说明
>
![结构说明](https://gitee.com/winglau/frontend_code_specification/raw/master/dir_img.png)

#### 2.HTML规范
>基于 W3C、苹果开发者 等官方文档，并结合团队业务和开发过程中总结的规范约定，让页面HTML代码更具语义性。
##### 2.1．嵌套元素应当缩进一次（用四个空格来代替制表符（tab）） -- 这是唯一能保证在所有环境下获得一致展现的方法。
##### 2.2．不要省略可选的结束标签（closing tag）（例如，</li> 或 </body>）。
##### 2.3．对于属性的定义，确保全部使用双引号，绝不要使用单引号。
##### 2.4．任何时候都要尽量使用最少的标签并保持最小的复杂度。尽量遵循 HTML 标准和语义，但是不要以牺牲实用性为代价。
##### 2.5．属性顺序（属性分组）：相关的属性声明应当归为一组。个人觉得class和Id,name写在前面就可以，跟着是data-*，其他的随便写。？？？（个人觉得返过来比较好吧）
##### 2.6．样式尽量不要写在标签上，特殊情况除外（如：动态要改变高度等样式）。
##### 2.7．区块划分最好备注一下；
##### 2.8．不同模块的标签要换行隔开，以便区分和代码阅读，并在开始前加备注；
##### 2.9．需要控制的标签给类名之类的，尽量避免直接控制标签
```$xslt
<p class=”text”></p>  
推荐 .text{}  而不是 p{}
```
#### 3.CSS规范
>统一规范团队 CSS 代码书写风格和使用 CSS 预编译语言LESS语法风格，提供常用媒体查询语句和浏览器私有属性引用，并从业务层面统一规范常用模块的引用。
##### 3.1.命名：(只能出现小写字符和破折号)用小写字母，用“-”连接字母，最多不能超过4个：xx-xx-xx-xx；
##### 3.2.样式名要尽量用贴切的单词，不要用单个字母或数字之类的
##### 3.3.用四个空格来代替制表符（tab）
##### 3.4.选择器分组时，将单独的选择器单独放在一行
```$xslt
.xxx,
.yy{
fontSize:14px;
}
```
##### 3.5.写备注
##### 3.6.非必须不用ID选择器
##### 3.7.样式书写顺序
```$xslt
1.位置属性(position, top, right, z-index, display, float等)
2.大小(width, height, padding, margin)
3.文字系列(font, line-height, letter-spacing, color- text-align等)
4.背景(background, border等)
5.其他(animation, transition等)
```

##### 3.8.简写样式顺序要规范，如：border:1px solid red;(这是比确正确的顺序),border:solid 1px red(这样写也可以，但不是很规范)，又如：background:red url() no-repeat fixed top;（应该比较正确的吧）等等。
##### 3.9.去掉小数的前面的零，如：font-size: 0.6px;写成font-size: .6px;
```$xslt
样式属性名与值之间（冒名后面）有个空格，如：
font-size:0.6px;（没空格的），font-size: 0.6px;（有空格的）
```

#### 4.图片规范
>了解各种图片格式特性，根据特性制定图片规范，包括但不限于图片的质量约定、图片引入方式、图片合并处理等，旨在从图片层面优化页面性能。
##### 4.1.图片格式
常见的图片格式有 GIF、PNG8、PNG24、JPEG、WEBP，根据图片格式的特性和场景需要选取适合的图片格式。
##### 4.2.内容图
* 开发阶段可以使用图片占位符如
```html
<img src="http://placeholder.qiniudn.com/300x200" />
```
![](http://placeholder.qiniudn.com/300x200)
* 内容图多以商品图等照片类图片形式存在，颜色较为丰富，文件体积较大
* 优先考虑 JPEG 格式，条件允许的话优先考虑 WebP 格式
* 尽量不使用PNG格式，PNG8 色位太低，PNG24 压缩率低，文件体积大
##### 4.3.背景图
背景图多为图标等颜色比较简单、文件体积不大、起修饰作用的图片

* PNG 与 GIF 格式，优先考虑使用 PNG 格式,PNG格式允许更多的颜色并提供更好的压缩率
* 图像颜色比较简单的，如纯色块线条图标，优先考虑使用 PNG8 格式，避免不使用 JPEG 格式
* 图像颜色丰富而且图片文件不太大的（40KB 以下）或有半透明效果的优先考虑 PNG24 格式
* 图像颜色丰富而且文件比较大的（40KB - 200KB）优先考虑 JPEG 格式
* 条件允许的，优先考虑 WebP 代替 PNG 和 JPEG 格式
#### 5.命名规范
>从 目录、图片、HTML/CSS文件、ClassName 的命名等层面约定规范团队的命名习惯，增强团队代码的可读性。

#### 6.JavaScript 规范
>统一团队的 JS 语法风格和书写习惯，减少程序出错的概率，其中也包含了 ES6 的语法规范和最佳实践。