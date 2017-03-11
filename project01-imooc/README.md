Project01-imooc
===============

### 一、查看：
    [点击查看]()

### 二、实现：

### 三、知识点：

#### 1 IE的渲染：
http://www.cnblogs.com/nidilzhang/archive/2010/01/09/1642887.html
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
  * **::selection 选择器：**
  **描述：**匹配被用户选取的部分；<br>
  **注意：**只能向`::selection`选择器应用少量的CSS属性，`color`、`background`、`cursor`、`outline`。

#### 7 !important

#### 8 CSS 属性：
  * **visibility 属性：**
  **描述：**规定元素是否可见<br>
  **值：**visible | hidden | collapse | inherit (默认值，可见 | 不可见 | 表格一行或一列处于不可见状态 | 继承父元素的设置)
  **注意：**即使不可见的元素也会占据原本的空间

  * **flex 属性：**
  **描述：**
  **值：**
  **注意：**

  * **zoom 属性：**
  **描述：**设置或检索对象的缩放比例；
  **值：**number | percentage (用浮点数来定义缩放比例 | 用百分比来定义缩放比例)
  **注意：**不允许使用负值

  * ** overflow属性：**
  **描述：**
  **值：**
  **注意：**

#### 9 清楚浮动的方法：
  * 添加一个空元素，并设置`clear:both;`如下：
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
  * 给父元素添加`overflow:auto;`样式，如下：
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
  * 使父元素和子元素一样，浮动起来，即给父元素设置`float:left|right;`；

  上面三种，或多或少都存在一些问题，因此，可以使用下面的方式：

  * 给父元素添加下面的样式：
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