# DOM事件
## DOM事件的传播
浏览器的事件模型，就是通过监听函数（listener）对事件做出反应。事件发生后，浏览器监听到了这个事件，就会执行对应的监听函数。

```
<div class=爷爷>
    <div class=爸爸>
        <div class=儿子>
        内容
        </div>
    </div>
</div>
```
当点击最内部元素儿子时，也会按顺序看看父元素上的监听函数，有就提供事件信息，没有就跳过。
由此可知：一个事件发生后，会在子元素和父元素中传播，具体分三个阶段：
1. 从最外层元素window对象传导到目标节点（由外到内），被称为捕获阶段，也叫事件捕获。
2. 在目标节点错发，称为目标阶段。
3. 从目标节点传导到最外层window对象（由内到外），被称为冒泡阶段，也叫事件冒泡。
在浏览器中，最外层对象是window，接着依次为document、html、body、body、outer、inter和center。
## 事件模型
### 原始事件模型（DOM0级）
监听函数可以直接在HTML标签上绑定或者通过JS绑定，但是同类型事件只能绑定一次，后面的会覆盖前面的。
### 标准事件模型（DOM2级）
通过JS的api：addEventListener(type,fn,bool)可以绑点监听函数
* type：表示事件类型，有100多种。
* fn：表示执行的函数。
* bool：表示是否在捕获阶段执行，默认值是false。

    <div class="div1">
        <p class="p1">
        <span class="span1">click</span>
        </p>
    </div> 
添加事件

    let div = document.querySelector('#div1');
    let p = document.querySelector('#p1');

    function fn(e) {
      let tagName = e.currentTarget.tagName;
      var phase = e.eventPhase;
      console.log(tagName, phase);
    }

    div.addEventListener('click',fn);
    p.addEventListener('click',fn);

点击，输出为：

    P 3
    Div 3

表示监听事件在冒泡阶段执行。
如果addEventListener传入第三个参数为true，输出为：

    Div 1
    P 1

表示监听事件在捕获阶段执行。
代码中e。currentTarget返回的是程序员监听的元素；eventPhase返回的是整数值，其中1为捕获阶段、2为事件对象触发阶段、3为冒泡阶段。
e.stopPropagation()可以用来中断冒泡。
## 事件委托
由于事件会在冒泡阶段向上传播到父节点，因此可以把子节点的监听函数定义在父节点上，由父节点的监听函数统一处理多个子元素的事件。这种方法叫做事件的委托。
这样可以节省内存，监听动态元素。
[on('click', '#testDiv', 'li', fn)函数，功能是当用户点击#testDiv 里的li元素时，调用fn函数](http://js.jirengu.com/geqapidika/14/watch?html,js,console,output)


