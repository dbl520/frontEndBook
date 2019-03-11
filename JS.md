# GitBook
#获取今天明天后天
```
  //类似2018-7-9
  GetDateStr(0);//今天()
  GetDateStr(1);//明天
  GetDateStr(2);//后天
      // 获取今天明天后天
    GetDateStr(AddDayCount) {
      var dd = new Date();
      dd.setDate(dd.getDate() + AddDayCount); //获取AddDayCount天后的日期
      var y = dd.getFullYear();
      var m = dd.getMonth() + 1; //获取当前月份的日期
      var d = dd.getDate();
      return y + "-" + m + "-" + d;
    },
```
# 前端知识点
  # 数组去重
```
    var arr = [2,3,4,4,5,2,3,6];
    var arr2 = arr.filter(function(element,index,self){
    return self.indexOf(element) === index;
    });
    console.log(arr2);
```
```
java  环境变量
变量名：JAVA_HOME    变量值：F:\java_jdk\jdk1.8

变量名：Path                  变量值：.;%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin;

变量名：classpath        变量值：.;%JAVA_HOME%\lib;%JAVA_HOME%\lib\tools.jar
```
```
  // 排序
   compare(obj1, obj2) {
    var val1 = obj1.unit; 
    var val2 = obj2.unit; 
      if ( val1 < val2 )  { 
        return -1; 
      } else if ( val1 > val2 ) { return 1; 
      } else {
        return 0;
      }
  },
   # 调用
    array.sort(this.compare)
```

```
去emjoy正则
   result = result.replace(/[\uD83C|\uD83D|\uD83E][\uDC00-\uDFFF][\u200D|\uFE0F]|[\uD83C|\uD83D|\uD83E][\uDC00-\uDFFF]|[0-9|*|#]\uFE0F\u20E3|[0-9|#]\u20E3|[\u203C-\u3299]\uFE0F\u200D|[\u203C-\u3299]\uFE0F|[\u2122-\u2B55]|\u303D|[\A9|\AE]\u3030|\uA9|\uAE|\u3030/g, "");
```
```
 常用方法:
获取节点：
document.getElementById(idName)          //通过id号来获取元素，返回一个元素对象
document.getElementsByName(name)       //通过name属性获取id号，返回元素对象数组
document.getElementsByClassName(className)   //通过class来获取元素，返回元素对象数组（ie8以上才有）
document.getElementsByTagName(tagName)       //通过标签名获取元素，返回元素对象数组
获取/设置元素的属性值：
element.getAttribute(attributeName)     //括号传入属性名，返回对应属性的属性值
element.setAttribute(attributeName,attributeValue)    //传入属性名及设置的值
创建节点Node：
document.createElement("h3")       //创建一个html元素，这里以创建h3元素为例
document.createTextNode(String); //创建一个文本节点；
document.createAttribute("class"); //创建一个属性节点，这里以创建class属性为例
增添节点：
element.appendChild(Node);   //往element内部最后面添加一个节点，参数是节点类型
elelment.insertBefore(newNode,existingNode); //在element内部的中在existingNode前面插入newNode
删除节点：
element.removeChild(Node)    //删除当前节点下指定的子节点，删除成功返回该被删除的节点，否则返回null
 
常用属性:
获取当前元素的父节点 ：
element.parentNode     //返回当前元素的父节点对象
获取当前元素的子节点：
element.chlidren        //返回当前元素所有子元素节点对象，只返回HTML节点
element.chilidNodes   //返回当前元素多有子节点，包括文本，HTML，属性节点。（回车也会当做一个节点）
element.firstChild      //返回当前元素的第一个子节点对象
element.lastChild       //返回当前元素的最后一个子节点对象
获取当前元素的同级元素：
element.nextSibling          //返回当前元素的下一个同级元素 没有就返回null
element.previousSibling   //返回当前元素上一个同级元素 没有就返回null
获取当前元素的文本：
element.innerHTML   //返回元素的所有文本，包括html代码
element.innerText     //返回当前元素的自身及子代所有文本值，只是文本内容，不包括html代码
获取当前节点的节点类型：node.nodeType   //返回节点的类型,数字形式（1-12）常见几个1：元素节点，2：属性节点，3：文本节点。
设置样式：element.style.color=“#eea”;      //设置元素的样式时使用style，这里以设置文字颜色为例。
```

 ```
  https://www.cnblogs.com/faithZZZ/p/6999327.html   call 跟apply用法主要是继承更更改this作用域
  
  
  方法定义
apply
Function.apply(obj,args)方法能接收两个参数：

obj：这个对象将代替Function类里this对象

args：这个是数组或类数组，apply方法把这个集合中的元素作为参数传递给被调用的函数。

 

call

call方法与apply方法的第一个参数是一样的，只不过第二个参数是一个参数列表

在非严格模式下当我们第一个参数传递为null或undefined时，函数体内的this会指向默认的宿主对象，在浏览器中则是window

1
2
3
4
5
var test = function(){
  console.log(this===window);
}
test.apply(null);//true
test.call(undefined);//true
用法

"劫持"别人的方法

此时foo中的logName方法将被bar引用 ，this指向了bar

1
2
3
4
5
6
7
8
9
10
var foo = {
  name:"mingming",
  logName:function(){
    console.log(this.name);
  }
}
var bar={
  name:"xiaowang"
};
foo.logName.call(bar);//xiaowang
实现继承

1
2
3
4
5
6
7
8
9
10
11
12
13
function Animal(name){   
  this.name = name;   
  this.showName = function(){   
    console.log(this.name);   
  }   
}   
 
function Cat(name){  
  Animal.call(this, name);  
}   
 
var cat = new Cat("Black Cat");   
cat.showName(); //Black Cat
在实际开发中，经常会遇到this指向被不经意改变的场景。
有一个局部的fun方法，fun被作为普通函数调用时，fun内部的this指向了window，但我们往往是想让它指向该#test节点，见如下代码：

1
2
3
4
5
6
7
8
window.id="window";
document.querySelector('#test').onclick = function(){
  console.log(this.id);//test
  var fun = function(){
    console.log(this.id);
  }
  fun();//window
}
使用call,apply我们就可以轻松的解决这种问题了

1
2
3
4
5
6
7
8
window.id="window";
document.querySelector('#test').onclick = function(){
  console.log(this.id);//test
  var fun = function(){
    console.log(this.id);
  }
  fun.call(this);//test
}
当然你也可以这样做，不过在ECMAScript 5的strict模式下，这种情况下的this已经被规定为不会指向全局对象，而是undefined：

1
2
3
4
5
6
7
8
9
window.id="window";
document.querySelector('#test').onclick = function(){
  var that = this;
  console.log(this.id);//test
  var fun = function(){
    console.log(that.id);
  }
  fun();//test
}
1
2
3
4
5
function func(){
  "use strict"
  alert ( this );  // 输出：undefined
}
func();
其他用法

类数组

这里把符合以下条件的对象称为类数组

1.具有length属性

2.按索引方式存储数据

3.不具有数组的push,pop等方法

常见类数组有 arguments,NodeList!

1
2
3
4
(function(){
  Array.prototype.push.call(arguments,4);
  console.log(arguments);//[1, 2, 3, 4]
})(1,2,3)
这样就往arguments中push一个4进去了

Array.prototype.push 页可以实现两个数组合并

同样push方法没有提供push一个数组,但是它提供了push(param1,param,…paramN) 所以同样也可以通过apply来装换一下这个数组,即:

1
2
3
4
var arr1=new Array("1","2","3"); 
var arr2=new Array("4","5","6"); 
Array.prototype.push.apply(arr1,arr2); 
console.log(arr1);//["1", "2", "3", "4", "5", "6"]
也可以这样理解,arr1调用了push方法,参数是通过apply将数组装换为参数列表的集合.

再比如我想求类数组中的最大值

1
2
3
4
(function(){
  var maxNum = Math.max.apply(null,arguments);
  console.log(maxNum);//56
})(34,2,56);
判断类型

1
2
3
4
5
6
7
console.log(Object.prototype.toString.call(123)) //[object Number]
console.log(Object.prototype.toString.call('123')) //[object String]
console.log(Object.prototype.toString.call(undefined)) //[object Undefined]
console.log(Object.prototype.toString.call(true)) //[object Boolean]
console.log(Object.prototype.toString.call({})) //[object Object]
console.log(Object.prototype.toString.call([])) //[object Array]
console.log(Object.prototype.toString.call(function(){})) //[object Function]
以上就是apply与call的用法总结的全部内容
 ```
