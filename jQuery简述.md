# jquery简述
jQuery是一个简洁的JavaScript框架，它封装JavaScript常用的功能代码，提供了一种简便的JavaScript设计模式，优化了HTML文档操作、事件处理、动画设计和Ajax交互。目前是最广泛的JavaScript库之一。主要功能有DOM属性操作、CSS属性操作、工具方法、特殊效果和事件操作。
## DOM操作
使用jQuery(选择器)可以获取到HTML的元素，但是它的返回值不是这个元素，而是一个可以操作这些元素的对象（API）。jQuery可简写为$。
获取元素

```
$("#xxx")//获取id为xxx的元素
$(".xxx")//获取类名为xxx的元素
$("#xxx>.xxx")//获取id为xxx里面类名为xxx的元素
$("#xxx").find(".xxx")//获取id为xxx里面类名为xxx的元素
$("#xxx").parent()//获取id为xxx元素的所有父元素
$("#xxx").children()//获取id为xxx元素的所有子元素
$("#xxx").siblings()//获取id为xxx元素的所有兄弟元素
$("#xxx").index()//从id为xxx元素获取到子元素的索引值
$("#xxx").next()//获取id为xxx元素的后一个元素
$("#xxx").prev()//获取id为xxx元素的前一个元素
$("#xxx").each(fn)//遍历元素并对每个元素执行fn函数
$div.get()//获取div中所有元素，组成数组
$div.get(0)//获取div中第一个元素
$div[0]//获取div中第一个元素
```
创建元素
```
$("<div>1</div>")//创建一个div元素的api对象
$("<div>1</div>").appendTO(body)//将div元素新增到body元素里面
```
增加元素
```
$("body").append(<div>1</div>)//body内部元素最后添加div元素
$("body").prepend(div)//body内部元素第一个添加div元素
$("#test").after(div)//id为test的元素后添加div元素
$("#test").before(div)//id为test的元素前添加div元素
```
删除元素
```
$div.remove()//删除div元素
$div.empty()//清空div的内容和子元素，保留div元素标签
```
修改元素
```
$div.text(xxx)//括号中无参数，表示查看div的文本内容；有参数时表示更改文本内容
$div.html(xxx)//括号中无参数，表示查看div的html内容；有参数时表示更改html内容
$div.attr('title',xxx)//读取或写入div中的title值
$div.css(propertyName,value)//读取或写入div中css的属性与值
```
通过参数数量的不同，使函数获得不同的功能，这种设计模式叫做函数重载。
还可以通过

    $('div').find('h3').eq(2).html('Hello')//在div子元素找到h3元素选择第三个将他的内容改成hello
    $('div').find('h3').eq(2).html('Hello').end().eq(0).html("world")//在div子元素找到h3元素选择第三个将他的内容改成hello,再返回h3元素选择第一个将他的内容改成world

这种在选择了元素后，不断进行函数操作，从而链接成链条形式的方法叫链式风格。

## jQuery原型
jQuery构造出来的对象有prototype属性，它包含了jQuery的所有共有属性。
用$.fn = $.prototype修改了名字，将api__proto__指向了$.fn。



