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
