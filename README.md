# Learning-Notes
数组的相关方法
新增：影响原数组
使用 array.push() 和 array.unshift() 新增元素会影响原来的数组。
**array.push( )**可以接受任意参数，把他们逐个添加至数组末尾， 返回修改后的数组长度，是一个数字，改变原数组

var arr = ["a","b","c","d"]
var arr2 =arr.push("e")
console.log(arr,arr2)  // ["a","b","c","d","e"]   5

array.ushift( ) 可以接受任意参数，把他们逐个添加至数组最前端， 返回修改后的数组长度，是一个数字，改变原数组，

   var arr = ["a","b","c","d"]
   var arr2 =arr.unshift("e")
   console.log(arr,arr2)  // ["e", "a", "b", "c", "d"] 5
新增：不影响原数组
两种方式新增元素不会影响原数组，第一种是 array.concat() 。
**array.concat( )**方法创建并返回一个新数组，不改变原数组

var arr = ["1","2","3"]
arr2 = arr.concat("a",[8,[9,10]]);
//  当参数中有一个数组时，会直接添加在后面合并成一个数组，如果是一个二维数组，则只会合并第一层数组中的数据，保留二维数组

console.log(arr,arr2)  //  (3) ["1", "2", "3"] (6) ["1", "2", "3", "a", 8, Array(2)]

第二种方法是使用 JavaScript 的展开（spread）操作符，展开操作符是三个点（…）

const arr1 = ['a', 'b', 'c', 'd', 'e'];
const arr2 = [...arr1, 'f']; // ['a', 'b', 'c', 'd', 'e', 'f']  
const arr3 = ['z', ...arr1]; // ['z', 'a', 'b', 'c', 'd', 'e']
展开操作符会复制原来的数组，从原数组取出所有元素，然后存入新的环境。


移除：影响原数组
使用 array.pop() 和 array.shift() 移除数组元素时，会影响原来的数组。
array.pop( ) 从数组末尾移出一项，没有参数，返回被移出的这一项，是一个字符串，影响原数组

       var arr = ["a","b","c","d"]
            var arr2 =arr.pop()
           console.log(arr,arr2)  // ["a","b","c",]  "d"
array.shift() 从数组第一项移出一项，没有参数，返回被移出的这一项，是一个字符串，影响原数组

       var arr = ["a","b","c","d"]
       var arr2 =arr.shift()
       console.log(arr,arr2)  // ["b", "c", "d"]  "a"
delete array[ ] 参数为数字，代表将元数组中的第几位元素移出，empty占位， 返回布尔值，改变原数组，但不改变长度

var arr = ["a","b","c","d"]
var arr2 =delete arr[1]
console.log(arr,arr2,arr.length)  //  ["a", empty, "c", "d"] true  4
array.pop() 和 array.shift() 返回被移除的元素，你可以通过一个变量获取被移除的元素。

array.splice() 一共有3个参数，第一个参数为从开始项，第二个参数为移除内容的长度，第三个参数是可选参数，以及第三个之后的参数均为要替换到数组中的内容，返回移出的内容

var arr = [1,3,2,3,4]
arr.splice(1,2,5,6,7)
console.log(arr)       //[1, 5, 6, 7, 3, 4]
如果第一个参数为0，则表示从第一个开始，如果第二个参数为0，则表示不移除元素，如果没有第三个参数，则表示不需要替换


移除：不影响原数组
array.filter() 参数为一个函数，函数接受2个参数，第一个item,为数组的每一项，第二个index为数组的下标，基于原数组创建一个新数组，新数组仅包含匹配特定条件的元素。

       var arr1 = ['a', 'b', 'c', 'd', 'e'];
       var arr2 = arr1.filter(item => item  !== 'e');  //["a", "b", "c", "d"]
       var arr3 = arr1.filter(item => item == 'e');  //["e"]    
头函数的独特性：
单行箭头函数，’return’ 关键字是默认自带的，不需要手动书写。
可是，多行箭头函数就需要明确地返回一个值。

array.slice()（不要与 array.splice() 混淆）
array.slice() 用以截取数组中的某一个片段，参数为2个数字，用逗号隔开，第一个为开始，第二个为结束，截取内容不包含结束项

var arr = [1,2,3,4,5]
arr2=arr.slice(2,4);   //从第二项（数字3）开始截取，截止到第4项，不包含第四项
console.log(arr,arr2)  //   (5)[1, 2, 3, 4, 5]  (2) [3, 4]
1)参数只有1个数字，则这个表示截取的起始位置，返回的数组包含开始项到数组中所剩余的所有项
arr3=arr.slice(2);
console.log(arr,arr3) //(5) [1, 2, 3, 4, 5] (3) [3, 4, 5]


2)参数有一个为负数，代表结束位置为数组中倒数第几位
arr4=arr.slice(-2);
console.log(arr,arr4) //(5) [1, 2, 3, 4, 5] (3) [ 4, 5]
arr5=arr.slice(1,-2);
console.log(arr,arr5) //[1, 2, 3, 4, 5] (2) [2, 3]


3)两个参数都为负数，同样是从数组最后开始数，从1开始计数，不包含结束项
arr6=arr.slice(-2,-3);
console.log(arr,arr6) //[1, 2, 3, 4, 5] (2) []
arr6=arr.slice(-3,-2);
console.log(arr,arr6) //[1, 2, 3, 4, 5] (2) [ 3


替换：影响原数组
array.splice( ) 如果知道替换哪一个元素，可以使用这个方法
一共有3个参数，第一个参数为从开始项，第二个参数为移除内容的长度，第三个参数是可选参数，以及第三个之后的参数均为要替换到数组中的内容，返回移出的内容

var arr = [1,3,2,3,4]
arr.splice(1,2,5,6,7)
console.log(arr)       //[1, 5, 6, 7, 3, 4]
如果第一个参数为0，则表示从第一个开始，如果第二个参数为0，则表示不移除元素，如果没有第三个参数，则表示不需要替换


替换：不影响原数组
array.map() 创建一个新数组，并且可以检查每一个元素，根据特定的条件替换它们。
参数为一个函数，函数可以接受3个参数，第一个item代表数组的每一项，第二个index代表每项的索引值，第三项为数组本身，返回一个新数组，不影响原数组

const arr1 = ['a', 'b', 'c', 'd', 'e']  
const arr2 = arr1.map(item => {  
 if(item === 'c') {
   item = 'CAT';
 }
 return item;
}); // ['a', 'b', 'CAT', 'd', 'e']

排序：改变原数组
array.reverse( ) 没有参数，返回排序后的数组，方法会将原有的数组顺序翻转，不产生新的数组，改变原数组

   var arr = ["a","b","c","d"]
   var arr2 =arr.reverse()
   console.log(arr,arr2)  //  ["d", "c", "b", "a"]  ["d", "c", "b", "a"]
array.sort( ) 方法会按照升序的方式进行排序，返回排序后的数组，改变原数组，

1)不带参数的时候，以字母表顺序排序

var arr = ["a","c","b","d"]
var arr2 =arr.sort();
console.log(arr,arr2)    //   ["a", "b", "c", "d"]
2)如果需要以数值的大小来进行排序，则可以传入一个回调函数来处理（要求数组中必须都是数字）

var arr = ["1","5","3","4"] 
arr2=arr.sort(function(a,b){
		return a-b;   //返回数组从小到大排序
		return b-a;      //返回数组从大到小排列
});
console.log(arr,arr2)  //      ["1", "3", "4", "5"]

数组转换
array.join( ) ：数组转字符串
将数组中所有的元素都转化为字符串并连接在一起，返回最后生成的字符串。（ 也是String.split()方法的逆向操作，后者是将字符串分割成若干块来创建一个数组）

Array.from(类数组[,回调函数])：类数组转数组
有三个参数，第一个参数为我们需要转换的类数组， 第二个参数是一个回调函数，转换之后需要执行的代码可以写在这里(凡是写在 [ ] 括号中的参数为可选参数，可传可不传)，第三个为this指向
返回一个新的数组，不影响原数组

console.log(Array.from("123"));   //["1", "2", "3"]

检测一个值是否是数组
Array.isArray( val ) 参数为需要检测的内容，返回布尔值，不影响原数组

		let arr = [1,2,3];
		let arr2 = {1:1,2:3}
		console.log( Array.isArray(arr))  //true
		console.log( Array.isArray(arr2))  //false

遍历数组每一项
方法：
Array.prototype.forEach (function(item,index,array){}[,this指向])

参数：
第一个参数为函数：，函数中的参数如下：
item：数组中的每一项
index：数组的下标
array: 原数组

第二个参数为 this 指向，是可选项

是否影响原数组
不影响

返回值:
如果没有在函数中return 的话 ，返回undefined

查找数组中首位满足条件的值
方法：
Array.prototype.findIndex(function(item,index,array){}[,this指向])

参数：
第一个参数为函数：，函数中的参数如下：
item：数组中的每一项
index：数组的下标
array: 原数组

第二个参数为 this 指向，是可选项

是否影响原数组
不影响

返回值:
有满足项:返回满足条件的的数据下标（find方法返回的事满足该条件的数据）
没有满足项：返回-1

查找数组中首位满足条件的值
方法：
Array.prototype.find (function(item,index,array){}[,this指向])

参数：
第一个参数为函数：，函数中的参数如下：
item：数组中的每一项
index：数组的下标
array: 原数组

第二个参数为 this 指向，是可选项

是否影响原数组
不影响

返回值:
有满足项:返回满足条件的的数据（findIndex方法返回的事满足条件数组的下标）
没有满足项：返回 undefined


文献推荐： https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array
