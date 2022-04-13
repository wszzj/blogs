# JavaScript函数
函数是一段可以反复调用的代码块。函数还能接受输入的参数，不同的参数会返回不同的值。
## 函数的声明

    function 函数名(形式参数1，形式参数2){
        return 返回值;
    }

当函数有函数名时，该函数叫做具名函数，否则叫匿名函数。可简写成箭头函数

    let f1 = x => x*x
    let f2 = (x,y) => x*y//参数有多个，要加圆括号
    let f1 = (x,y) => {return x*y}//返回值是语句时要加大括号
    let f1 = (x,y) => ({age:x,age:y})//返回值是对象时要加圆括号

所有的函数都是用Function函数构造出来的。

    let fn = new Function(x,y){return x+y}//不常用

## 函数的要素
每个函数都有：
* 调用时机：在调用函数前的最后一步，判断函数的返回值。
* 作用域：函数外部声明的变量是全局变量，可以在函数内使用；函数内部声明的变量是局部变量，外部无法调用。window属性可以全局调用。
* 闭包：函数嵌套，可用函数的子函数在函数外部调用到函数的参数。如果哟个函数用到了外部的变量，那么这个函数和这个变量就叫做闭包。
* 形式参数：函数运行的时候，有时需要提供外部数据，不同的外部数据会得到不同的结果，这种外部数据就叫参数。参数可以省略。
* 返回值：return后面就是返回值，如果没有return，返回值为undefined。
* 调用栈：调用函数时，需要把函数的环境push到一个数组里，等函数执行完，会把环境从数组pop出来，这个数组就是调用栈。当函数的里面有它自己，这样的函数叫递归函数。在递归函数中，如果push次数过多，会出现爆栈的情况。
* 函数提升：JavaScript引擎会把函数名视作变量名，提升到代码头部。
* arguments（除了箭头函数）：arguments对象包含了函数运行时的所有参数，可以通货修改arguments[x]来修改参数的值，但是在函数对象里面加上'user strict'代码可以强制无法修改参数值。arguments是一个伪数组，可以通过Array.prototype.slice.call(arguments)来转换成数组。
* this（除了箭头函数）：this就是属性或方法“当前”所在的对象。调用this可以有下面两种方法：
    
    arr.fn()
    arr.fn.call(arr)
    arr.fn(1)
    arr.fn.call(arr,1)

使用.bind可以绑定this。

## JavaScript的执行时机

    let i = 0
    for(i = 0; i<6; i++){
    setTimeout(()=>{
    console.log(i)
    },0)
    }//结果是6个6

setTimeout方法会在for循环语句执行完之后，再执行打印语句，所以会打出6个最终的i值。
在最新的ES6中，可以用下面的代码打印出不同的结果。
    
    for(let i = 0; i<6; i++){
    setTimeout(()=>{
    console.log(i)
    },0)
    }//结果是0,1,2,3,4,5

还可以用下面的代码打出0,1,2,3,4,5的结果：

    let i = 0
    function fn(i) {
      if (i < 6) {
        console.log(i)
        i = i + 1
        fn(i)
      }
    }
    fn(i)



