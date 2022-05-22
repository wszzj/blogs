# MVC初解
MVC是model、view、controller即模型、识图、控制器的缩写，他是一种设计模式。主要是用来分离不同作用代码的，当需要增加或者更改业务时，不需要再重新编写业务逻辑，减轻工作量。
* model：主要用来操作数据。
* view：主要用于操作页面。
* controller：其他。例如事件绑定等。

## EventBus
EventBus又称为事件总线，是给所有组件共用的事件中心。
它的API有
* on：在选定的元素上绑定一个或多个事件处理函数。
* trigger：根据绑定到匹配元素的给定的事件类型执行所有的处理程序和行为。
* off：移除一个事件处理函数。
```
import $ from 'jquery'
class EventBus{
    constructor(){
        this._eventBus = $(window)
    }
    on(eventName,fn){
        return this._eventBus.on(eventName,fn)
    }
    trigger(eventName,data){
        return this._eventBus.trigger(eventName,data)
    }
    off(eventName,fn){
        return this._eventBus.off(eventName,fn)
    }
}
```
## 表驱动编程
表驱动方法是一种使你可以在表中查找信息，而不必用逻辑语句（if或case）来把他们找出来的方法。在JS中，表就是指的哈希表结构，使用表驱动编程，能使重复冗余的代码变的稳定简洁。

## 模块化
模块化是一种处理复杂系统分解为更好的可管理模块的方式。
所谓的模块化开发就是封装细节，提供使用接口，彼此之间互不影响，每个模块都是实现某一特定的功能。模块化开发使用代码耦合度降低，最大化的设计重用，便于维护测试，但是也会造成内存使用过大，损耗性能。
