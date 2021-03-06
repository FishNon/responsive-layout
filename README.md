响应式布局
========

## 零、 响应式布局：

### 项目一：慕课自适应网站布局
* 源码地址：[点击查看](https://github.com/FishNon/responsive-layout/tree/master/project01-imooc)
* 效果演示：[点击查看](https://fishnon.github.io/responsive-layout/project01-imooc/)

## 一、 基础内容：

### 1 页面布局：

* 静态布局
* 弹性布局
* 自适应布局
* 流式布局
* 响应式布局：是一个设计理念，是多项技术的综合体

### 2 响应式布局的三大技术成分：

* 流动网格（弹性网格布局）
* 弹性图片
* 媒介查询

### 3 媒体查询

* [菜鸟教程：响应式web开发-媒体查询](http://www.runoob.com/css/css-rwd-mediaqueries.html)
* [菜鸟教程：@media查询](http://www.runoob.com/cssref/css3-pr-mediaquery.html)
* [菜鸟教程：媒介类型](http://www.runoob.com/css/css-mediatypes.html)
* 语法：
  ```
    @media mediaType and|or|not|only (media feature){
        CSS-Code;
    }
  ```
* 注意：
    or等价于逗号，因此逗号和or可以相互替代；<br>
    如果省略mediaType，则默认为```all```；<br>
* 举例：
  ```
    @media not screen and (max-width : 300px){
        body{
            background : #eee;
        }
    }
  ```

### 4 视口：

#### 基本概念：

* CSS属性 - 视口宽度（viewport）
  width：
  height:

* CSS属性 - 屏幕宽度

* 对于手机浏览器：有三个视口，分别为布局视口（layout viewport）、可视视口（visual viewport）、理想视口（ideal viewport）

#### 理想视口：

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

### 5 分析设计图：

* 与设计师沟通交流，是否有相应设计规范（字体、颜色、字号、间距等）；
* 根据针对不同设备制作的设计图，分析哪里是不变的，哪里时可变的；
* 分析结构（如：头部区域、广告区域、产品展示区域、底部导航区域、版权区域等）

### 6 响应式网站设计实践原则：

* 渐进增强：即先构建一个简单的基本效果，再根据浏览器、分辨率不同的特点，逐渐的追加新功能；<br>
  优雅降级：先做出最终、最优秀的状态，然后根据哪些浏览器没有哪些功能就去掉哪些效果；<br>
  （根据自己的喜好、团队的偏向选择渐进增强或优雅降级）<br>

* 不管设备大小，应该包含相同的内容；<br>
  根据设备大小的不同，显示不同的内容；<br>

* 断点的选择<br>
  断点就是媒体查询中的临界点，一般来说媒体查询最常用的属性就是宽度（最大宽度、最小宽度）。<br>
  宽度数值（断点）的选择决定了响应式设计的分界点；<br>
  * 针对设备进行断点选择
  * 将设备大小分成几大类型来进行断点的选择（例如：0-480_小屏幕，481-800_中屏幕，801-1400_大屏幕，1400以上_超大屏幕）

## 二、 项目目录结构的组织（如何组织项目目录结构）：

* 约定优于配置（按约定编程）
* 约定代码结构或命名规范来减少配置数量
* css/demo.css | style/demo.css | ...
* 脚本文件（原文件）demo.js - 脚本文件（压缩后）demo.min.js
总而言之，目录结构的搭建，仍旧根据个人、团队的习惯、偏好约定设置。


## 三、 相关资料：

* [网页的布局方式](http://blog.csdn.net/gertyy/article/details/52764527)
* [网页布局](http://mt.sohu.com/20161107/n472512749.shtml)