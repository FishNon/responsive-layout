Project01-imooc
===============

### 查看：


### 实现：

### 知识点：

* IE的渲染：
http://www.cnblogs.com/nidilzhang/archive/2010/01/09/1642887.html
```
<meta http-equiv="x-ua-compatible" content="ie=edge">
```
`ie=edge`表示强制以最新的IE浏览器模式渲染页面

* 理想视口：
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

* IE的条件注释：
相关链接：http://www.admin10000.com/Document/21.html
```
<!--[if lte IE8]>
    statement;
<![endif]-->
```
[更新浏览器](http://browsehappy.com/)

* CSS resets 及 Normalize.css
[Normalize 官网](http://necolas.github.io/normalize.css/)

* 单位：
  * px : 相对于屏幕分辨率的单位，1px相当于1个像素
  * em : 相对长度单位;
    1. em的相对参考物是父元素的`font-size`;
    2. em具有继承的特点;
    3. 当没有设置`font-size`时，浏览器会有一个默认的em设置：`1em = 16px`;
    4. em的缺点：容易混乱
  * rem : 相对参照物为根元素html，相对于参照物固定不变;当没有设置`font-size`时，浏览器会有一个默认的`rem`值，`1rem = 16px`;

