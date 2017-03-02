响应式布局
========

## 1. 基础内容：

#### 页面布局：

* 静态布局
* 弹性布局
* 自适应布局
* 流式布局
* 响应式布局：是一个设计理念，是多项技术的综合体

#### 响应式布局的三大技术成分：

* 流动网格（弹性网格布局）
* 弹性图片
* 媒介查询

#### 媒体查询

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
  
* CSS属性 - 视口宽度（viewport）
  width：

* CSS属性 - 屏幕宽度

#### 对于手机浏览器：

* 手机浏览器有三个视口，分别为：布局视口（layout viewport）、可视视口（visual viewport）、理想视口（ideal viewport）



## 2. 响应式布局：


### 相关资料：

* [网页的布局方式](http://blog.csdn.net/gertyy/article/details/52764527)
* [网页布局](http://mt.sohu.com/20161107/n472512749.shtml)