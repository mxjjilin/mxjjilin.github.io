---
title: sass的学习1
date: 2017-05-16 20:04:39
tags: 技术总结
---
![](http://static.open-open.com/news/uploadImg/20160220/20160220113201_326.png)

通过ruby安装sass，然后就可以开始学习了。做个总结如下：
1，SCSS 是 Sass 的新语法格式，从外形上来判断他和 CSS 长得几乎是一模一样，代码都包裹在一对大括号里，并且末尾结束处都有一个分号。其文件名格式常常以“.scss”为扩展名。
2，编译方式一般有三种，命令编译，界面工具编译，自动化编译。命令编译为：sass <要编译的Sass文件路径>/style.scss:<要输出CSS文件路径>/style.css。
3，输出方式：sass --watch test.scss:test.css --style nested 嵌套输出；sass --watch test.scss:test.css --style expanded 展开输出；sass --watch test.scss:test.css --style compact 紧凑输出；sass --watch test.scss:test.css --style compressed 压缩输出；
4，嵌套：.box {               
  font: {
   size: 12px;
   weight: bold;
  }  
}
.box {
     font-size: 12px;
     font-weight: bold;
}
属性嵌套；
.box{
  &:before {
    content:"伪元素嵌套";
  }
}
.box:before {
  content: "伪元素嵌套"; }
伪类嵌套；
5，混合宏
@mixin border-radius($radius){
  -webkit-border-radius: $radius;
  border-radius: $radius;
}
.box {
  @include border-radius(3px);
}
6，继承
.btn {
  border: 1px solid #ccc;
  padding: 6px 10px;
  font-size: 14px;
}
.btn-primary {
  color: #fff;
  @extend .btn;
}
结果
.btn, .btn-primary {
  border: 1px solid #ccc;
  padding: 6px 10px;
  font-size: 14px; }

.btn-primary {
  color: #fff; }
7，占位符
%mt5 {
  margin-top: 5px;
}
.btn {
  @extend %mt5;
}
结果
.btn { margin-top: 5px; }
8，混合宏 VS 继承 VS 占位符
混合宏可以传递参数，但代码容易冗余；继承不可传递参数，代码清晰；占位符不调用不会产生代码；
9，插值

























