# web前端规范整理
前言

本人根据网上一些资源整理的前端规范。有错误的请大家纠正，随时issue我

# 目录
* HTML 编写规范 (#HTML)
* CSS 编写规范


## 命名规则

### 项目命名跟文件文件命名

全部采用小写方式， 以下划线分隔。（避免驼峰式命名）
例：my_project_name,  account_model.js , retina_sprites.scss , error_report.html

### 目录命名

参照项目命名规则；
有复数结构时，要采用 **复数** 命名法。

例：scripts, styles, images, data_models



## HTML 编写规范 {#HTML}
### 语法
用两个空格来代替制表符(tab)-- 这是唯一能保证在所有环境下获得一致展现的方法。
嵌套元素应当缩进一次(即两个空格)。
  对于属性的定义,确保全部使用双引号,绝不要使用单引号。
不要在自闭合(self-closing)元素的尾部添加斜线 --HTML5 规范中明确说明这是可选 的。
不要省略可选的结束标签(closing tag)(例如,</li> 或 </body>)。

    <!DOCTYPE html>
    <html>
    <head>
    <title>Page title</title>
    </head> <body>
    <img src="images/company-logo.png" alt="Company">
    <h1 class="hello-world">Hello, world!</h1> </body>
    </html>

### Html5 doctype
为每个 HTML 页面的第一行添加标准模式(standardmode)的声明,这样能够确保在 每个浏览器中拥有一致的展现。

    <!DOCTYPE html>
    <html>
        <head>
        </head>
    </html>

### 语言属性(Language attribute)
根据 HTML5 规范:
强烈建议为 html 根元素指定 lang 属性,从而为文档设置正确的语言。这将有助于语 音合成工具确定其所应该采用的发音,有助于翻译工具确定其翻译时所应遵守的规则等等。
更多关于 lang 属性的知识可以从 此规范 中了解。
<html lang="zh-CN">
<!-- ... --> </html>


### 字符编码
通过明确声明字符编码,能够确保浏览器快速并容易的判断页面内容的渲染方式。这样 做的好处是,可以避免在 HTML 中使用字符实体标记(character entity),从而全部与文档 编码一致(一般采用 UTF-8 编码)。
<head>
<meta charset="UTF-8">
</head>

### IE 兼容样式
IE 支持通过特定的 <meta> 标签来确定绘制当前页面所应该采用的 IE 版本。除非有
强烈的特殊需求,否则最好是设置为 edgemode,从而通知 IE 采用其所支持的最新的模式。 `<meta http-equiv="X-UA-Compatible" content="IE=Edge">`

### 引入 CSS 和 javascript 文件
根据 HTML5 规范,在引入 CSS 和 JavaScript 文件时一般不需要指定 type 属性,因
为 text/css 和 text/javascript 分别是它们的默认值。 <!-- External CSS -->

    <link rel="stylesheet" href="code-guide.css">
    <!-- In-document CSS --> <style>
    /* ... */ </style>
    <!-- JavaScript -->
    <script src="code-guide.js"></script>

### 实用为王
尽量遵循 HTML 标准和语义,但是不要以牺牲实用性为代价。任何时候都要尽量使用
最少的标签并保持最小的复杂度。
1.1.8 属性顺序
HTML 属性应当按照以下给出的顺序依次排列,确保代码的易读性。
class
id, name
data-*
src, for, type, href title, alt
aria-*, role
2
class 用于标识高度可复用组件,因此应该排在首位。id 用于标识具体组件,应当谨慎 使用(例如,页面内的书签),因此排在第二位。
<a class="..." id="..." data-modal="toggle" href="#"> Example link
</a>
<input class="form-control" type="text">
<img src="..." alt="...">

### 布尔(boolean)型属性
布尔型属性可以在声明时不赋值。XHTML 规范要求为其赋值,但是 HTML5 规范不
需要。
元素的布尔型属性如果有值,就是 true,如果没有值,就是 false。
如果一定要为其赋值的话,请参考 WhatWG 规范:
如果属性存在,其值必须是空字符串或 [...] 属性的规范名称,并且不要再收尾添加空 白符。
  简单来说,就是不用赋值。

    <input type="text" disabled>
    <input type="checkbox" value="1" checked> <select>
    <option value="1" selected>1</option> </select>

### 减少标签数量
编写 HTML 代码时,尽量避免多余的父元素。很多时候,这需要迭代和重构来实现。
请看下面的案例:

    <!-- Not so great --> <span class="avatar">
    <img src="..."> </span>
    <!-- Better -->
    <img class="avatar" src="...">

### Javascript 生成的标签

通过 JavaScript 生成的标签让内容变得不易查找、编辑,并且降低性能。能避免时尽量 避免。


### 属性顺序

属性应该按照特定的顺序出现以保证易读性；

* class
* id
* name
* data-*
* src, for, type, href, value , max-length, max, min, pattern
* placeholder, title, alt
* aria-*, role
* required, readonly, disabled

class是为高可复用组件设计的，所以应处在第一位；

id更加具体且应该尽量少使用，所以将它放在第二位。

## CSS 编写规范 {#CSS}



## javascript编写规范 {#标记}


以上文档是根据多个网上的文献资源跟文章整理的,仅供学习交流.


参考文献:

1、腾讯团队
百度：[ecomfe/spec · GitHub ] [1]

[1]: https://link.zhihu.com/?target=https%3A//github.com/ecomfe/spec    "Baidu"

2、腾讯AlloyTeam：[Code Guide by @AlloyTeam] [2]

[2]:https://link.zhihu.com/?target=http%3A//alloyteam.github.io/CodeGuide/     "AlloyTeam"

3、GitHub：[Styleguide · GitHub][3]

[3]:https://link.zhihu.com/?target=https%3A//github.com/styleguide     "Styleguide · GitHub"

