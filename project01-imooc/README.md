Project01-imooc
===============

### 一、效果演示：
 * [点击查看](https://fishnon.github.io/responsive-layout/project01-imooc/)
 * 使用`http-server`运行访问：
   * [下载安装NodeJs](http://nodejs.cn/download/)
   * 全局环境下安装`http-server`：
   ```
      npm install http-server -g
   ```
   * 运行：
   ```
      http-server
   ```
   * 运行后会获得两个http地址，使用本机连个地址都能访问，但是使用其他设备只能访问到第二个地址；

### 二、技术点：
 * 第三部分的知识点；
 * 第三方组件：
     * 轮播：[官网 OwlCarousel2](http://owlcarousel2.github.io/OwlCarousel2/)
     * [CDN OwlCarousel2 ](https://cdnjs.com/libraries/OwlCarousel2)
       设置`owl.theme.default.min.css`文件的内容；
     * jQuery：[官网 jQuery](http://jquery.com/)
     * 处理响应式图片兼容性问题的库：[官网 picturefill](http://scottjehl.github.io/picturefill/)
     * [官网 http-server](https://www.npmjs.com/package/http-server)
 * 工具：
     * [在线绘制SVG图片](http://editor.method.ac/)
     * [在线绘制SVG图片](https://icomoon.io/)
     * [在线快速搜索查看兼容性](http://caniuse.com/)
     * [在线压缩SVG图片](http://iconizr.com/)
     * [在线压缩PNG/JPG图片](https://tinypng.com/)

### 三、知识点：

#### 1 IE的渲染：
相关链接：[使用X-UA-Compatible来设置IE浏览器兼容模式](http://www.cnblogs.com/nidilzhang/archive/2010/01/09/1642887.html)
```
<meta http-equiv="x-ua-compatible" content="ie=edge">
```
`ie=edge`表示强制以最新的IE浏览器模式渲染页面

#### 2 理想视口：
  * 理想视口就是布局视口在一个设备上的最佳尺寸；
  * 使用理想视口（使用视口元标签）：
  ```
      <meta name="viewPort" content="
          width=device-width,  // 将布局视口设置为理想视口
          minimun-scale=1.0,   // 最小的缩放比例
          maximun-scale=1.0,   // 最大的缩放比例
          user-scalable=no,    // 禁止用户缩放
          initial-scale=1.0"   // 默认缩放比例
      />
  ```

#### 3 IE的条件注释：
相关链接：http://www.admin10000.com/Document/21.html
```
<!--[if lte IE8]>
    statement;
<![endif]-->
```
[更新浏览器](http://browsehappy.com/)

#### 4 CSS resets 及 Normalize.css
[Normalize 官网](http://necolas.github.io/normalize.css/)

#### 5 单位：
  * px : 相对于屏幕分辨率的单位，1px相当于1个像素
  * em : 相对长度单位;
    * em的相对参考物是父元素的`font-size`;
    * em具有继承的特点;
    * 当没有设置`font-size`时，浏览器会有一个默认的em设置：`1em = 16px`;
    * em的缺点：容易混乱
  * rem : 相对参照物为根元素html，相对于参照物固定不变;
    * 当没有设置`font-size`时，浏览器会有一个默认的`rem`值，`1rem = 16px`;
    * 缺点：部分浏览器不支持
    * 兼容方式（在设置`font-size`时，同时进行下面两种设置）：
    ```
        font-size : 16px;
        font-size : 1rem;
    ```
    * 计算：
    ```
        font-size : 62.5% --- 1rem = 10px --- (10/16*100%)
        font-size : 100%  --- 1rem = 16px
    ```

#### 6 CSS 选择器：
  * **基本选择器：**
    * 通配符选择器（*）：匹配所有的元素，或某个元素下面的所有元素`div *`；
    * 元素选择器（Element）
    * 类选择器（.class）
    * ID选择器（#id）
    * 后代（包含）选择器（Element Element）：可以是子元素、孙子元素等
    * 子元素选择器（Element > Element）：只能选择某个元素的直接子元素；
    * 相邻兄弟选择器（Element1 + Element2）：能够选择**紧跟**在Element1之后的Element2元素，两个元素有相同的父元素；
    * 通用兄弟选择器（Element1 ~ Element2）：选择与Element1 元素相邻的后面的所有的兄弟元素；
  * **属性选择器：**
    * Element[attr]：匹配所有定义了`attr`属性的元素；
    * Element[attr = "value"]：匹配所有定义了`attr`属性，且属性值为`value`的元素；
    * Element[attr ^= "value"]：匹配所有定义了`attr`属性，且属性值以`value`开头的元素；
    * Element[attr $= "value"]：匹配所有定义了`attr`属性，且属性值以`value`结尾的元素；
    * Element[attr *= "value"]：匹配所有定义了`attr`属性，且属性值包含`value`的元素；
    * Element[attr ~= "value"]：匹配所有定义了`attr`属性，且属性值包含`value`的元素，即使是包含空格的属性值，也可以模糊的选择到；
    * Element[attr != "value"]：匹配所有定义了`attr`属性，且属性值以`value`或`value-`开头的元素
  * **伪类和伪元素选择器：**
    * :link、:visited、:hover、:active、:focus；
    * :enabled（启用）、:disabled（禁用）、:checked（选中）；
    * :first-child：选择某个元素的第一个元素；
    * :last-child：选择某个元素的最后一个元素；
    * :nth-child()：匹配括号中指定的子元素，括号里可以是表达式（如：2n表示选中0、2、4...）、也可以是整数值，此外还可以使用`even`表示偶数，使用`odd`表示奇数；
    * :nth-last-child(n)：同`:nth-child()`，只是是从后向前匹配而已；
    * :nth-of-type()：匹配括号中指定的同类型子元素；
    * :nth-last-of-child()：同`:nth-of-type()`，只是是从后向前匹配而已；
    * :first-of-type：匹配属于其父元素的首个子元素的每个元素；
    * :last-of-type：匹配属于其父元素的最后一个子元素的每个元素；
    * :only-child：匹配属于其父元素的唯一子元素的每个元素；
    * :only-of-type：匹配属于其父元素的唯一指定类型的子元素的每个元素；
    * :empty：匹配没有任何子节点的元素，即使是空格也没有；
    * :not(selector)：匹配非selector元素外的所有元素；
    * :first-line：匹配指定元素的首行，`p:first-line`（匹配所有p元素的第一行）；
    * :first-letter：匹配指定元素的首字母，`p:first-letter`（匹配所有p元素的第一个字母）；
    * :before：配合`content`属性使用，在元素前面添加内容；
    * :after：配合`content`属性使用，在元后面添加内容；
    * ::selection：匹配被用户选取的部分；只能向`::selection`选择器应用少量的CSS属性，`color`、`background`、`cursor`、`outline`。

#### 7 !important

#### 8 CSS 属性：
  * **visibility 属性：**<br>
  **描述：**规定元素是否可见<br>
  **值：**visible | hidden | collapse | inherit (默认值，可见 | 不可见 | 表格一行或一列处于不可见状态 | 继承父元素的设置)<br>
  **注意：**即使不可见的元素也会占据原本的空间<br>

  * **flex 属性：**<br>
  **描述：**<br>
  **值：**<br>
  **注意：**<br>

  * **zoom 属性：**<br>
  **描述：**设置或检索对象的缩放比例；<br>
  **值：**number | percentage (用浮点数来定义缩放比例 | 用百分比来定义缩放比例)<br>
  **注意：**不允许使用负值<br>

  * ** overflow属性：**<br>
  **描述：**<br>
  **值：**<br>
  **注意：**<br>

  * ** vertical-align属性：**<br>
  **描述：**<br>
  **值：**<br>
  **注意：**<br>

  * ** text-overflow属性：**<br>
  **描述：**<br>
  **值：**<br>
  **注意：**<br>

  * ** white-space属性：**<br>
  **描述：**<br>
  **值：**<br>
  **注意：**<br>

  * ** cursor属性：**<br>
  **描述：**<br>
  **值：**<br>
  **注意：**<br>

  * ** filter属性：**<br>
  **描述：**<br>
  **值：**<br>
  **注意：**<br>

  * ** page-break-inside属性：**<br>
  **描述：**<br>
  **值：**<br>
  **注意：**<br>

  * ** page-break-after属性：**<br>
  **描述：**<br>
  **值：**<br>
  **注意：**<br>

  * ** page-break-before属性：**<br>
  **描述：**<br>
  **值：**<br>
  **注意：**<br>

  * ** orphans属性：**<br>
  **描述：**<br>
  **值：**<br>
  **注意：**<br>

  * ** widows属性：**<br>
  **描述：**<br>
  **值：**<br>
  **注意：**<br>

  * ** calc()属性：**<br>
  **描述：**动态计算长度值（eg.width），支持+、-、×、/<br>
  **使用：**如：`width : calc(100% - 10px);`<br>
  **注意：**使用标准的数学运算优先级规则<br>

#### 9 清楚浮动的方法：
  * 添加一个空元素，并设置`clear:both;`如下：<br>
  ```
  <style>
    .container{
        background: lightgrey;
    }
    .demo{
        float: left;
        width:120px;
        height:200px;
    }
  </style>
  <div class="container">
      <div class="demo">模块一</div>
      <div class="demo">模块二</div>
      <div style="clear: both"></div>
  </div>
  ```
  * 给父元素添加`overflow:auto;`样式，如下：<br>
  ```
  <style>
      .container{
          overflow: auto;
          background: lightgrey;
      }
      .demo{
          float: left;
          width:120px;
          height:200px;
      }
  </style>
  <div class="container">
      <div class="demo">模块一</div>
      <div class="demo">模块二</div>
  </div>
  ```
  * 使父元素和子元素一样，浮动起来，即给父元素设置`float:left|right;`；<br>

  上面三种，或多或少都存在一些问题，因此，可以使用下面的方式：<br>

  * 给父元素添加下面的样式：<br>
  ```
    .clearfix:after{
        content : '';
        display : block;
        height : 0;
        clear : both;
        visibility : hidden;
    }
    /*这句主要用于兼容IE6、IE7*/
    .clearfix{
        zoom : 1;
    }
  ```
  * 或给父元素添加下面的样式：<br>
  ```
  .clearfix:after,
  .clearfix:before {
      content: '';
      display: block;
  }
  .clearfix:after {
      clear: both;
  }
  ```

#### 10 CSS定位规则——BFC与IFC
 **BFC**（Block Formatting Contexts）
  * 定义：直译为“块级格式化上下文”，是web页面中盒型布局的CSS渲染模式，其本质上是页面上的一个隔离的渲染区域，容器里面的子元素不会在布局上影响到外面的元素，反之也是如此；
  * 一个BFC是一个`HTML`盒子并且至少满足下列条件中的任何一个:
    * `float`的值不为`none`；
    * `position`的值不为`static`或`relative`；
    * `display`的值为`table-cell`、`table-caption`、`inline-block`、`flex`或`inline-flex`中的一个；
    * `overflow`的值不为`visible`；
  * 应用：多栏布局等


 **IFC**（Inline Formatting Contexts）
 * 定义：直译为“内联格式化上下文”，IFC的`line box`（线框）高度由其包含行内元素中最高的实际高度计算而来。
 * 注意：IFC中的`line box`一般左右都是贴紧着整个IFC，但是会因为`float`元素而扰乱。
 * 应用：水平居中、垂直居中


 **GFC**（GridLayout Formatting Contexts）
 * 定义：直译为“网格布局格式化上下文”，当为一个元素设置`display`值的`grid`的时候，此元素将会获得一个独立的渲染区域，可以通过网格容器上定义网格定义行和网格定义列属性各在网格项目上定义网格行和网格列为每一个网格项目定义位置和空间。
 * 优点：GridLayout会有更加丰富的属性来控制行列，控制对齐以及更为精细的渲染语义和控制。


 **FFC**（Flex Formatting Contexts）
 * 定义：直译为“自适应格式化上下文”，`display`值为`flex`或`inline-flex`可以得到一个伸缩容器。设置为`flex`的容器被渲染为一个块级元素，而被设置为`inline-flex`的容器则被渲染为一个行内元素；
 * 其他：伸缩容器中的每一个子元素都是一个伸缩元素。伸缩元素可以时任意数量的。伸缩元素外和伸缩元素内 的一切元素都不影响。即，`Flexbox`定义了伸缩容器内伸缩项目该如何布局。


 **相关链接：**
  * [CSS中的BFC、IFC、GFC、FFC](http://www.cnblogs.com/dingyufenglian/p/4845477.html)
  * [理解CSS中的BFC](http://www.w3cplus.com/css/understanding-block-formatting-contexts-in-css.html)

#### 11 响应式图片：
 * 响应式图片主要指：<br>
   ① 图片排版和布局的响应式；<br>
   ② 根据设备大小加载不同的图片；<br>
 * 实现方式：<br>
   ① JS或服务端来控制图片的加载；<br>

   ```
   // 前提：链接jQuery库
   $(document).ready(function(){
      function makeImageResponsive(){
        var width = $(window).width();
        var img = $(".content img");
        if(width <= 480){
          img.attr('src','img/480.png');
        }else if(width <= 800){
          img.attr('src','img/800.png');
        }else{
            img.attr('src','img/1600.png');
        }
      }
   })
   $(window).on('realize load' , makeImageResponsive)
   ```

   ② `srcset`<br>

   ```
   <img src="img/480.png"
        srcset="img/480.png 480w, img/800.png 800w, img/1600.png 1600w">
   ```

   ③ `srcset`配合`sizes`<br>

   ```
   <img src="img/480.png"
           srcset="img/480.png 480w, img/800.png 800w, img/1600.png 1600w"
           sizes:"(min-width:800px) 800px, 100vw">
   ```

   ④ `picture`<br>

   ```
   <picture>
      <source media="(min-width:36em)"
              srcset="img/demo01.png 768w" />
      <source srcset="img/demo02.png 1800w" />
      <img class="image" src="img/demo02.png">
   </picture>
   ```
   ⑤ SVG<br>