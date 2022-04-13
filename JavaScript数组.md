# JavaScript数组
数组是按次序排列的一组值，用方括号包住，每个值都有一个字符串下标。其本质就是对象，键名为一般从0开始的字符串，键值是数组成员，可以是任意数据类型。
数组自身属性length表示数组的长度，等于最大键名+1。
## 声明一个数组

    let arr0 = [1,2,3]//简洁写法
    let arr1 = new Array(1,2,3)//规范写法
    let arr2 = new Array(3)//声明一个长度为3的空数组

也可以通过转化字符串得到一个数组,合并两个数组为一个数组。

    let arr0 = '1,2,3'.split(',')
    let arr1 = '123'.split(',')
    Array.from('123')//这三行代码都会得到一个[1,2,3]的数组
    arr2.concat(arr3)//合并形成一个新数组
    arr4.slice(1)//截取下标1以及后面的值组成新数组
    
还可以通过函数创建类似数组的数组（伪数组），它的样式与数组相同，但是没有数组的原型。

    let divList = document.querySelectorAll('div')

## 删除数组值
删除数组的值，数组的长度不会改变，删除位置的值会变成empty。

    delete arr[0]//删除数组第一个值
    arr.length(3)//会从第三个值开始删除数组中后面的所有值
    arr0.shift()//数组第一个值被删除
    arr0.pop()//数组最后一个值被删除
    arr.splice(1,1)//删除arr数组的1号下标后的第一个值
    arr.splice(1,1,'a','b')//删除arr数组的1号下标后的第一个值并在此处插入'a''b'值

## 查看数组索引和值

    Object.keys(arr)//查看所有索引
    for(let key in arr){console.log(`${key}:${arr[key]}`)}//遍历数组所有索引和值
    arr.forEach(function(item,index){
        console.log(`${index}:${item}`)
        })//使用forEach共有索引遍历数组所有索引和值
    arr[0]//查看数组第一个值
    arr.indexOf(item)//查看arr中item的索引，若没有返回-1
    arr.find(item => item%2 == 0)//找到第一个偶数，返回值
    arr.findIndex(item => item%2 == 0)//找到第一个偶数，返回索引

## 添加数组值

    arr.push(newItem)//尾部添加新值newItem，返回新长度
    arr.unshift(newItem)//头部添加新值newItem，返回新长度
    arr.splice(1,0,'x')//在数组1索引位置后面添加'x'值
    arr.reverse()//反转数组
    arr.sort((a,b) => a-b)//数组值从大到小排序，字符串放最后

## 数形变换

    let arr = [0, 1, 2, 2, 3, 3, 3, 4, 4, 4, 4, 6];
    let arr2 = arr.map(i => {
        const a = {
        0: '周日',
        1: '周一',
        2: '周二',
        3: '周三',
        4: '周四',
        5: '周五',
        6: '周六',
        }
        return a[i]
    });
    console.log(arr2);//可以将数值替换成字符串，n对n替换
    //
    let scores = [95,91,59,55,42,82,72,85,67,66,55,91];
    let scores2 = scores.filter(item => item > 60);
    console.log(scores2);//可以将数组长度减少，n对少于n替换
    //
    let scores = [95,91,59,55,42,82,72,85,67,66,55,91];
    let sum = scores.reduce((sum, n)=> sum+(n%2===1?n:0)
    ,0);
    console.log(sum);//可以将数组长度减少到1个，n对1替换




    


