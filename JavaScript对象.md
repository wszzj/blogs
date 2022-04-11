# JavaScript对象
对象（object）是JavaScript语言的核心概念，也是七种数据类型｛数值（number）；字符串（string）；布尔（boolean）；symbol（符号ES6）；未定义（undefined）；空（null）；对象（object）｝中最重要的数据类型。
对象是一组“键值对”（key-value）的集合，是一种无序的数据集合。

    let obj = {
        'name' : '小明',
        'age' : 18
    }

上面代码中，大括号定义了一个对象，指向变量obj。name是键名（对象的键名也叫做属性），'小明'是键值，中间用冒号隔开。以上是简洁写法，规范写法是：

    let obj = new Object({
        'name' : '小明',
        'age' : 18  
        }
    )

对象的属性都是字符串，如果要省略引号，属性要按标识符规范命名。使用Object.keys(obj)可以得到obj的所以自身属性。
使用变量作为属性时需要加上[]。

    let a = 'name'
    let obj1 = {a:'jack'}//此时属性是'a'
    let obj2 = {[a]:'jack'}//此时属性是'name'

## 对象删除属性

    delete obj.xxx
    delete obj['xxx']

上面代码可以删除对象中的xxx属性，使用'xxx' in obj 返回值查看属性xxx是否被删除。使用'xxx' in obj&&obj.xxx === undefined,当返回值为true时，xxx属性的值就是undefined。

## 对象查看属性

    Object.keys(obj)//查看obj的所有自身属性
    console.dir(obj)//查看obj所有自身加共有属性
    obj.hasOwnProperty(xxx)//当返回值为true时，说明这个xxx属性是obj对象自身的属性；当返回值为false时，说明这个xxx属性可能是obj对象共有的属性或者obj对象没有这个属性。
    'xxx' in obj//当返回值为true时，说明这个xxx属性是obj对象自身或共有的属性；当返回值为false时，说明这个obj对象没有xxx这个属性。
    obj.['key']//查看obj对象的key属性的属性值
    obj.key//查看obj对象的key属性的属性值
    obj.[key]//查看key变量属性的属性值

## 对象修改或增加属性
对象的公有属性无法通过自身修改，最好不要修改原型上的属性。

    let obj1 = {}
    let obj2 = {}
    obj1.toString = 'xxx'
    obj2.toString = undefined//改变obj1的toString共有属性值，obj2的并不会改变。

增加属性时，当原对象有此属性，就修改属性；当原对象没有此属性，就添加此属性。

    obj.xxx = 'xxx'
    obj['xxx'] = 'xxx'//这两句相同意思，都是添加或修改xxx属性的值为'xxx'
    obj.assign(obj,{xxx:'xxx',......})//添加或修改多组键值对
    Object.prototype['toString'] = 'xxx'//修改共有属性值为'xxx'
    //
    let common ={}
    let obj = Object.create(common)//obj.prototype会变成common对象的属性

