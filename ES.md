# GitBook

# 前端知识点

---

**小程序图片预览，current是当前图片的src**
```
<!DOCTYPE html>
<html lang="en" onclick="alert('html')">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <script src="http://cdn.static.runoob.com/libs/jquery/1.10.2/jquery.min.js"></script>
    <title>Document</title>
</head>
<body onclick="alert('body')">
    <!--html-->
    <div style="width:400px; height:400px; background:red" onclick="alert(this.style.background)">
            <div id="div2" style="width:300px; height:300px; background:palevioletred">
                    <div style="width:200px; height:200px; background:yellow" onclick="alert(this.style.background)">
                            <div id="div1" style="width:100px; height:100px; background:palegreen">
                                <a id="aaa" href="http://www.baidu.com">aaa</a> 
                            </div>
                    </div>
            </div>
    </div>

    <script>
        //此jquery既阻止默认行为又停止冒泡
        // $("#div1").on('click',function(){
        //     return false;
        // });

        window.onload = function () {
            var oDiv1 = document.getElementById('div1');
            var oDiv2 = document.getElementById('div2');

            oDiv1.onclick = function (ev){
                var oEvent = ev || event;
                alert("this is div1");
                
                //js阻止事件冒泡
                //oEvent.cancelBubble = true;
                //oEvent.stopPropagation();

                //js阻止链接默认行为，没有停止冒泡
                //oEvent.preventDefault(); 
                //return false;
            }

            oDiv2.onclick = function (ev){
                var oEvent = ev || event;
                alert("this is div2");
                oEvent.cancelBubble = true; 
            }
        }
    </script>
</body>
</html>
```
# js常用方法
# 1.输出语句：document.write(""); 
# 2.JS中的注释为//
# 3.传统的HTML文档顺序是:document->html->(head,body)
# 4.一个浏览器窗口中的DOM顺序是:window->(navigator,screen,history,location,document)
# 5.得到表单中元素的名称和值:document.getElementById("表单中元素的ID号").name(或value)
```
6.一个小写转大写的JS: document.getElementById("output").value = document.getElementById("input").value.toUpperCase();
7.JS中的值类型:String,Number,Boolean,Null,Object,Function
8.JS中的字符型转换成数值型:parseInt(),parseFloat()
9.JS中的数字转换成字符型:(""+变量)
10.JS中的取字符串长度是:(length)
11.JS中的字符与字符相连接使用+号.
12.JS中的比较操作符有:==等于,!=不等于,>,>=,<.<=
13.JS中声明变量使用:var来进行声明
14.JS中的判断语句结构:if(condition){}else{}
15.JS中的循环结构:for([initial e­xPRession];[condition];[upadte e­xpression]) {inside loop}
16.循环中止的命令是:break
17.JS中的函数定义:function functionName([parameter],...){statement[s]}
18.当文件中出现多个form表单时.可以用document.forms[0],document.forms[1]来代替.
19.窗口:打开窗口window.open(), 关闭一个窗口:window.close(), 窗口本身:self
20.状态栏的设置:window.status="字符";
21.弹出提示信息:window.alert("字符");
22.弹出确认框:window.confirm();
23.弹出输入提示框:window.prompt();
24.指定当前显示链接的位置:window.location.href="URL"
25.取出窗体中的所有表单的数量:document.forms.length
26.关闭文档的输出流:document.close();
27.字符串追加连接符:+=
28.创建一个文档元素:document.createElement(),document.createTextNode()
29.得到元素的方法:document.getElementById()
30.设置表单中所有文本型的成员的值为空:
```
```
var form = window.document.forms[0]
for (var i = 0; i<form.elements.length;i++){
     if (form.elements[i].type == "text"){
         form.elements[i].value = "";
     }
}
```
```
31.复选按钮在JS中判断是否选中:document.forms[0].checkThis.checked (checked属性代表为是否选中返回TRUE或FALSE)
32.单选按钮组(单选按钮的名称必须相同):取单选按钮组的长度document.forms[0].groupName.length
33.单选按钮组判断是否被选中也是用checked.
34.下拉列表框的值:document.forms[0].selectName.options[n].value (n有时用下拉列表框名称加上.selectedIndex来确定被选中的值)
35.字符串的定义:var myString = new String("This is lightsWord");
36.字符串转成大写:string.toUpperCase(); 字符串转成小写:string.toLowerCase();
37.返回字符串2在字符串1中出现的位置:String1.indexOf("String2")!=-1则说明没找到.
38.取字符串中指定位置的一个字符:StringA.charAt(9);
39.取出字符串中指定起点和终点的子字符串:stringA.substring(2,6);
40.数学函数:Math.PI(返回圆周率),Math.SQRT2(返回开方),Math.max(value1,value2)返回两个数中的最在值,Math.pow(value1,10)返回value1的十次方,Math.round(value1)四舍五入函数,Math.floor(Math.random()*(n+1))返回随机数
41.定义日期型变量:var today = new Date();
42.日期函数列表:
dateObj.getTime()得到时间,
dateObj.getYear()得到年份,
dateObj.getFullYear()得到四位的年份,
dateObj.getMonth()得到月份,
dateObj.getDate()得到日,
dateObj.getDay()得到日期几,
dateObj.getHours()得到小时,
dateObj.getMinutes()得到分,
dateObj.getSeconds()得到秒,
dateObj.setTime(value)设置时间,
dateObj.setYear(val)设置年,
dateObj.setMonth(val)设置月,
dateObj.setDate(val)设置日,
dateObj.setDay(val)设置星期几,
dateObj.setHours设置小时,
dateObj.setMinutes(val)设置分,
dateObj.setSeconds(val)设置秒 [注意:此日期时间从0开始计]
43.FRAME的表示方式:
[window.]frames[n].ObjFuncVarName,frames["frameName"].ObjFuncVarName,frameName.ObjFuncVarName
44.parent代表父亲对象,top代表最顶端对象
45.打开子窗口的父窗口为:opener
46.表示当前所属的位置:this
47.当在超链接中调用JS函数时用:(javascript:)来开头后面加函数名
48.在老的浏览器中不执行此JS:<!--      //-->
49.引用一个文件式的JS:<script type="text/Javascript" src="aaa.js"></script>
50.指定在不支持脚本的浏览器显示的HTML:<noscript></noscript>
51.当超链和ONCLICK事件都有时,则老版本的浏览器转向a.html,否则转向b.html.例:<a href="a.html" onclick="location.href='b.html';return false">dfsadf</a>
52.JS的内建对象有:Array,Boolean,Date,Error,EvalError,Function,Math,Number,Object,RangeError,ReferenceError,RegExp,String,SyntaxError,TypeError,URIError
53.JS中的换行:\n
54.窗口全屏大小:
<script>function fullScreen(){ this.moveTo(0,0);this.outerWidth=screen.availWidth;this.outerHeight=screen.availHeight;}window.maximize=fullScreen;</script>
55.JS中的all代表其下层的全部元素http://bizhi.knowsky.com/
56.JS中的焦点顺序:document.getElementByid("表单元素").tabIndex = 1
57.innerHTML的值是表单元素的值:如<p id="para">"how are <em>you</em>"</p>,则innerHTML的值就是:how are <em>you</em>
58.innerTEXT的值和上面的一样,只不过不会把<em>这种标记显示出来.
59.contentEditable可设置元素是否可被修改,isContentEditable返回是否可修改的状态.
60.isDisabled判断是否为禁止状态.disabled设置禁止状态
61.length取得长度,返回整型数值
62.addBehavior()是一种JS调用的外部函数文件其扩展名为.htc
63.window.focus()使当前的窗口在所有窗口之前.
64.blur()指失去焦点.与FOCUS()相反.
65.select()指元素为选中状态.
66.防止用户对文本框中输入文本:onfocus="this.blur()"
67.取出该元素在页面中出现的数量:document.all.tags("div(或其它HTML标记符)").length
68.JS中分为两种窗体输出:模态和非模态.window.showModaldialog(),window.showModeless()
69.状态栏文字的设置:window.status='文字',默认的状态栏文字设置:window.defaultStatus = '文字.';
70.添加到收藏夹:external.AddFavorite("http://www.xrss.cn","jaskdlf");
71.JS中遇到脚本错误时不做任何操作:window.onerror = doNothing; 指定错误句柄的语法为:window.onerror = handleError;
72.JS中指定当前打开窗口的父窗口:window.opener,支持opener.opener...的多重继续.
73.JS中的self指的是当前的窗口
74.JS中状态栏显示内容:window.status="内容"
75.JS中的top指的是框架集中最顶层的框架
76.JS中关闭当前的窗口:window.close();
77.JS中提出是否确认的框:if(confirm("Are you sure?")){alert("ok");}else{alert("Not Ok");}
78.JS中的窗口重定向:window.navigate("http://www.sina.com.cn");
79.JS中的打印:window.print()
80.JS中的提示输入框:window.prompt("message","defaultReply");
81.JS中的窗口滚动条:window.scroll(x,y)
82.JS中的窗口滚动到位置:window.scrollby
83.JS中设置时间间隔:setInterval("expr",msecDelay)或setInterval(funcRef,msecDelay)或setTimeout
84.JS中的模态显示在IE4+行,在NN中不行:showModalDialog("URL"[,arguments][,features]);
85.JS中的退出之前使用的句柄:function verifyClose(){event.returnValue="we really like you and hope you will stay longer.";}} window.onbeforeunload=verifyClose;
86.当窗体第一次调用时使用的文件句柄:onload()
87.当窗体关闭时调用的文件句柄:onunload()
88.window.location的属性: protocol(http:),hostname(www.example.com),port(80),host(www.example.com:80),pathname("/a/a.html"),hash("#giantGizmo",指跳转到相应的锚记),href(全部的信息)
89.window.location.reload()刷新当前页面.
89-1.parent.location.reload()刷新父亲对象（用于框架）
89-2.opener.location.reload()刷新父窗口对象（用于单开窗口）
89-3.top.location.reload()刷新最顶端对象（用于多开窗口）
90.window.history.back()返回上一页,window.history.forward()返回下一页,window.history.go(返回第几页,也可以使用访问过的URL)
91.document.write()不换行的输出,document.writeln()换行输出
92.document.body.noWrap=true;防止链接文字折行.
93.变量名.charAt(第几位),取该变量的第几位的字符.
94."abc".charCodeAt(第几个),返回第几个字符的ASCii码值.
95.字符串连接:string.concat(string2),或用+=进行连接
96.变量.indexOf("字符",起始位置),返回第一个出现的位置(从0开始计算)
97.string.lastIndexOf(searchString[,startIndex])最后一次出现的位置.
98.string.match(regExpression),判断字符是否匹配.
99.string.replace(regExpression,replaceString)替换现有字符串.
100.string.split(分隔符)返回一个数组存储值.
101.string.substr(start[,length])取从第几位到指定长度的字符串.
102.string.toLowerCase()使字符串全部变为小写.
103.string.toUpperCase()使全部字符变为大写.
104.parseInt(string[,radix(代表进制)])强制转换成整型.
105.parseFloat(string[,radix])强制转换成浮点型.
106.isNaN(变量):测试是否为数值型.
107.定义常量的关键字:const,定义变量的关键字:var
# 小程序wxparse富文本src补全路径
```
    var content = res.data.data.content;
    content = content.replace(/src=&quot;/g, "src=https://jisu.shenmikj.com");
    content = content.replace(/jpg\'\//g, "jpg'");
    content = content.replace(/.jpg&quot;\//g, `.jpg`);
    content = content.replace(/.png&quot;\//g, `.png`);
```
 # 单行css隐藏省略号
 ```
 1.overflow: hidden;
 2.text-overflow: ellipsis;
 3.white-space: nowrap;
 ```
 多行
 ```
 text-overflow: -o-ellipsis-lastline;  
 overflow: hidden;  
 text-overflow: ellipsis;  
 display: -webkit-box;  
 -webkit-line-clamp: 2;  
 -webkit-box-orient: vertical; 
```
```
<div>catchtap='preventClose' 小程序阻止冒泡事件</div>
```
```
<div>
    @keyframes fade-in {  
    0% {opacity: 0;}/*初始状态 透明度为0*/  
    40% {opacity: 0;}/*过渡状态 透明度为0*/  
    100% {opacity: 1;}/*结束状态 透明度为1*/  
    }  
    @-webkit-keyframes fade-in {/*针对webkit内核*/  
    0% {opacity: 0;}  
    40% {opacity: 0;}  
    100% {opacity: 1;}  
    }  
    #wrapper {    
    animation: fade-in;/*动画名称*/  
    animation-duration: 1.5s;/*动画持续时间*/  
</div>
```
微信公众号获取用户信息
用户授权并获取code ，使用code换取access_token 并使用access_token获取用户信息
    小程序里 ```<text>你好\n测试</text>``` 这样操作会换行

```
微信小程序中使用的布局还有样式，使用到的是前端的 css 
css 的样式可以写在 style 里面


属性

width: fit-content;
font-size:20px;      /*设置文字字号*/
color:red;           /*设置文字颜色*/
font-weight:bold;    /*设置字体加粗*/
border:1px solid red;/*添加边框样式（粗细为1px， 颜色为红色的实线）*/
font-family:"宋体";   /*设置字体为宋体*/

font-style:italic;    /*文字排版--斜体*/
text-decoration:underline;   /*文字排版--下划线*/
text-decoration:line-through;/*文字排版--删除线*/
text-indent:2em;             /*段落排版--缩进*/
line-height:1.5em;           /*段落排版--行间距（行高）*/
letter-spacing:50px;         /*段落排版--中文字间距*/
word-spacing:50px;           /*字母间距*/
text-align:center;  right ; left ;  /*段落排版--对齐*/

display:inline-flex;        /*将对象作为内联块级弹性伸缩盒显示*/
display:block;              /*设置为块状元素*/
display:inline;             /*设置为内联元素*/
display:inline-block;       /*设置为内联块状元素*/

word-break:keep-all;        /* 不换行 */ 
white-space:nowrap;         /* 不换行 */ 
vertical-align:middle;     /*把此元素放置在父元素的中部。*/

border-style（边框样式）常见样式有：  （border-color,border-width） 边框相关设置
dashed（虚线）| dotted（点线）| solid（实线）。
border-bottom border-top border-right border-left 上下左右线单独设置

box-sizing: border-box; //当使用padding的时候不影响大小
padding-top padding-right padding-bottom padding-left
margin-top margin-right margin-bottom margin-left (margin:10px 10px 10px 10px; top、right、bottom、left)
```

```
<view class='nav-item flex-row a-center j-center rpx32  {{current==index?"activeColor":""}}' bindtap='tabIndex' data-index="{{index}}">
        {{item}}
        <image src='../../images/icons/sort.png' class='sort-image' wx:if="{{current!=index }}"></image>
        <image src='../../images/icons/sort-aes.png' class='sort-image' wx:elif='{{current==index && orderBy == 1}}'></image>
        <image src='../../images/icons/sort-des.png' class='sort-image'  wx:elif='{{current==index && orderBy == 0}}'></image>
      </view>
      js部分
        // tab列表展示
  tabselect:function(e){
    var that =this;
    var index = e.currentTarget.dataset.index
    console.log(e)
    console.log(index)
    that.setData({
      current:index,
      orderbuy: that.data.current != index ? 1 : 1 - that.data.orderbuy
    })
  },
```
```
小程序中在scroll-view下文字换行并且二行省略
    font-size: 28rpx;
  color: #353535;
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-line-clamp: 2;
  overflow: hidden;
  margin-top: 20rpx;
  width: 280rpx;
  white-space:normal; 
  word-break:break-all;

```

#小程序视频组件
```
video{
  width: 100%;
  display: block;
}
```
#小程序遮罩层不滚动

```
.showhome {
  height: 100vh;
  overflow: hidden;
}

```
```
解决微信小程序滚动穿透问题
<view bindtap="hideCoupon" class='coupon_receive_wrapper {{showCouponFlag==true?"active":""}}' catchtouchmove="preventD">
...
</view>


复制代码
.coupon_receive_wrapper{
  display:none;
  position:fixed;
  left:0;
  top:0;
  right:0;
  bottom:0;
  width:100%;
  height:100%;
  background:rgba(0,0,0,.5);
  z-index:11;
  transition: all 1s ease;
}
.coupon_receive_wrapper.active{
  display:block;
}
js部分
preventD:function(){}
```
```
  小程序网络设置
 "networkTimeout": {
    "request": 60000,
    "downloadFile": 60000
  }
```
```
块级元素居中 html代码部分
<div class="parent">
   <div class="child">child</div>
</div>
行内元素居中 html代码部分
<div class="parent">
   <span class="child">child</span>
</div>


04 块级元素：绝对定位 + margin: auto;

优点：不需要提前知道尺寸，兼容性好
缺点：这个方法是我最喜欢用的一个，要说缺点的话，我目前还不知道。
此方法出自张鑫旭老师的博客 小tip: margin:auto实现绝对定位元素的水平垂直居中

.parent {
    position: relative;
    height: 200px;
}
.child {
    width: 80px;
    height: 40px;
    position: absolute;
    left: 0;
    top: 0;
    right: 0;
    bottom: 0;
    margin: auto;
    background: blue;
}

01 行内元素（单行文字垂直居中）：设置 line-height = height
.parent {
   height: 200px;
   line-height: 200px;
   border: 1px solid red;
}


07 块级元素：display: flex

缺点：兼容性不好

.parent {
    width: 600px;
    height: 200px;
    border: 1px solid red;
    display: flex;
    align-items: center;
    justify-content: center;  /*水平居中*/
}
.child {
    background: blue;
}

作者：Suplum
链接：https://juejin.im/post/5a7a9a545188257a892998ef
来源：掘金
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。

```

```
解决移动端1px问题
.block {
      width: 100px;
      height: 100px;
      margin: 10px;
      position: relative;
      /*border: 1px solid red;*/
}
.block:before {
      content: '';
      position: absolute;
      transform-origin: 0 0;
      top: 0;
      left: 0;
      width: 200%;
      height: 200%;
      border: 1px solid red;
      transform: scale(.5);
}

```
new Date().toLocaleString() //时间戳转字符串
```
```
// simple array
var arr = ['a', 'b', 'c'];
console.log(Object.keys(arr)); // console: ['0', '1', '2']
```
// array like object
var obj = { 0: 'a', 1: 'b', 2: 'c' };
console.log(Object.keys(obj)); // console: ['0', '1', '2']

// array like object with random key ordering
var anObj = { 100: 'a', 2: 'b', 7: 'c' };
console.log(Object.keys(anObj)); // console: ['2', '7', '100']

// getFoo is a property which isn't enumerable
var myObj = Object.create({}, {
  getFoo: {
    value: function () { return this.foo; }
  } 
});
myObj.foo = 1;
console.log(Object.keys(myObj)); // console: ['foo']
```
```
```
数组对象排序
var arr = [{name: "zlw", age: 24}, {name: "wlz", age: 25}];
var compare = function (obj1, obj2) {
    var val1 = obj1.name;
    var val2 = obj2.name;
    if (val1 < val2) {
        return -1;
    } else if (val1 > val2) {
        return 1;
    } else {
        return 0;
    }            
} 
console.log(arr.sort(compare));
```

```
   var newarray = Object.keys(res.data.data.heroData.heroInfo.equipname);
        var len = newarray.length;
        var skillvalue = res.data.data.heroData.heroInfo.equipname[Object.keys(res.data.data.heroData.heroInfo.equipname)[len - 1]]
        var skillvalue2 = res.data.data.heroData.heroInfo.equipname[Object.keys(res.data.data.heroData.heroInfo.equipname)[0]]
        var skill = newarray[len - 1];
```


```
正则把数字字符串变成number
  str = str.replace(/\"/g, "");  //正则去掉""
```

```
var Str = '1:00:00'
var Temp = Str.split(':')
var Seconds = 3600 * Number(Temp[0]) + 60 * Number(Temp[1]) + Number(Temp[2])
console.log(Seconds)
```
```
   // //  随机4个不重复的数据
    // function getRandomArrayElements(arr, count) {
    //   var shuffled = arr.slice(0), i = arr.length, min = i - count, temp, index;
    //   while (i-- > min) {
    //     index = Math.floor((i + 1) * Math.random());
    //     temp = shuffled[index];
    //     shuffled[index] = shuffled[i];
    //     shuffled[i] = temp;
    //   }
    //   return shuffled.slice(min);
    // }

    // console.log(getRandomArrayElements(newid, wx.getStorageSync("mydata")));
```

```
 vscode配置token     3087a62753b4f9325eaac164b8a8284b51bd6e49
```

```
es6数组去重
[...new Set(getData)]
```

# ES6相关
```
        块级作用区域 let a = 1;
        可定义常量 const PI = 3.141592654;
        变量解构赋值 var [a, b, c] = [1, 2, 3];
        字符串的扩展(模板字符串) var sum =${a + b};
        数组的扩展(转换数组类型) Array.from($('li'));
        函数的扩展(扩展运算符) [1, 2].push(...[3, 4, 5]);
        对象的扩展(同值相等算法) Object.is(NaN, NaN);
        新增数据类型(Symbol) let uid = Symbol('uid');
        新增数据结构(Map) let set = new Set([1, 2, 2, 3]);
        for...of循环 for(let val of arr){};
        Promise对象 var promise = new Promise(func);
        Generator函数 function* foo(x){yield x; return x*x;}
        引入Class(类) class Foo {}
        引入模块体系 export default func;
        引入async函数[ES7]
        async function asyncPrint(value, ms) {
        await timeout(ms);
        console.log(value)
        }
 ```
    

# Promise 的构造函数 构造一个 Promise，最基本的用法如下：    

```
       var promise = new Promise(function(resolve, reject) {

            if (...) {  // succeed

                resolve(result);

            } else {   // fails

                reject(Error(errMessage));

            }
        });
```

精通javascript
参考文献（两个文档混合看，非常有用）


阮一峰 es6 ：http://es6.ruanyifeng.com/#docs/object

MDN：https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Working_with_Objects

webpack打包：https://segmentfault.com/a/1190000006178770#articleHeader3

廖雪峰的js教程：https://www.liaoxuefeng.com/wiki/001434446689867b27157e896e74d51a89c25cc8b43bdb3000/001434499763408e24c210985d34edcabbca944b4239e20000

over


node.js

javascript : BOM DOM ECMASCRIPT
DOM：节点和属性、增删改查、事件
HTML
CSS
框架：JQuery、Vue、Wepy、Angular
快速学习能力
参考文献：http://www.w3school.com.cn/htmldom/dom_intro.asp

DOM


getElementById(id)
appendChild(node)
removeChild(node)
innerHTML
parentNode
childNodes
attributes


JQuery


jquery 安装

jquery语法
$(document).ready(function(){

--- jQuery functions go here ----

});


jquery 选择器
jquery事件
jquery 效果
jquery HTML处理
over


nodejs支持es6
'use strict'//加上这句声明
$ node test.js

let和const
{
    let b = 100;
    var c = 1;
}
console.log(b);//b is not defined
let命令所在的代码块内有效。
for循环的计数器，就很合适使用let命令。

var array = ['gaolong', 'xiaoming', 'xiaoli'];
for (let i = 0; i < array.length; i++) {}
console.log(i); //i is not defined, i只在for循环体内有效

var array = ['gaolong', 'xiaoming', 'xiaoli'];
var a = [];
for (let i = 0; i < array.length; i++) {
    a[i] = function () {
        console.log(i);
    }
}
a[2](); //此处数组中存放的是函数，所以可以直接执行a[i]();重点比较let i与 var i的不同

let不存在变量提升,var存在。即脚本未执行前var变量已经存在，只是值为undefined.

let暂时性死区，temporal dead zone
var tmp = 123;
if (true) {
    tmp = 'abc'; //referenceError。该区域已经被let 覆盖。
    let tmp; 
}
let不允许在相同作用域内，重复声明同一个变量。
因此，不能在函数内部重新声明参数。
ES5只有全局作用域和函数作用域，没有块级作用域.

因此会出现这两种情况：
第一：内层变量可能会覆盖外层变量。
var tmp = new Date();
function f() {
    console.log(tmp);
    if (false) {
        var tmp = 'hello wolrd';
    }
}
f(); //undefined ,该使用let
'use strict';
if (true) {
  function f() {}
}
f(); // ReferenceError: f is not defined,es6函数在块级作用域内，外部不能使用。
第二：用来计数的循环变量泄露为全局变量。

const
只读常量，不能改变。
'use strict';
const pi = 3.14159;
pi // 3.14159
pi = 3; typeerror: pi is read-only
//如果是常规模式，不会报错，但是赋值无效
//const 一旦声明就必须赋值，const foo，报错
const的作用域与let命令相同：只在声明所在的块级作用域内有效。
const命令声明的常量也是不提升，同样存在暂时性死区，只能在声明的位置后使用
const声明的常量，也与let一样不可重复声明。

对于复合类型的变量，变量名不指向数据，而是指向数据所在的地址。const命令只是保证变量名指向的地址不变，并不保证该地址的数据不变，所以将一个对象声明为常量必须非常小心。
const foo = {}
foo.prop = 123;
foo.prop ;// 123
foo = {} //type error ;foo is readonly
const a = [];
a.push('Hello');//ok
a.length = 0; //ok
a = ["schiller"]; //error
如果真的想将对象冻结，应该使用Object.freeze方法。

 全局对象属性
 全局对象是最顶层的对象，在浏览器环境指的是window对象，在Node.js指的是global对象。ES5之中，全局对象的属性与全局变量是等价的。
 var a = 1;
// 如果在Node的REPL环境，可以写成global.a
// 或者采用通用方法，写成this.a
window.a // 1

let b = 1;
window.b // undefined
上面代码中，全局变量a由var命令声明，所以它是全局对象的属性；全局变量b由let命令声明，所以它不是全局对象的属性，返回undefined。


解构赋值
//注意，解构赋值在node环境中暂且无法运行，具体原因待探究，可以使用新建rn项目 //跑来测试
ES6允许按照一定模式，从数组和对象中提取值，对变量进行赋值，这被称为解构（Destructuring）。
var [a, b, c] = [1, 2, 3];
let [x, y, ...z] = ['a'];
// x = 'a', y = undefined, z = []
如果解构不成功，变量的值就等于undefined。
如果等号右边不是数组，严格的说不是可遍历结构，那将会报错。
//报错
let [foo] = 1;
let [foo] = false;
let [foo] = NaN;
let [foo] = undefined;
let [foo] = null;
let [foo] = {};
上面的表达式都会报错，因为等号右边的值，要么转为对象以后不具备Iterator接口（前五个表达式），要么本身就不具备Iterator接口（最后一个表达式）
事实上，只要某种数据结构具有Iterator接口，都可以采用数组形式的解构赋值。
function* fibs() {
  var a = 0;
  var b = 1;
  while (true) {
   yield a;
    [a, b] = [b, a+b]; 
  }
}
var [first ,second, third, fourth, fifth, sixth] = fibs();
sixth //5
默认值
var [foo = true] = [];
foo //true
ES6内部使用严格相等运算符（===），判断一个位置是否有值。所以，如果一个数组成员不严格等于undefined，默认值是不会生效的。
如：
[x, y = 'b'] = ['a']; // x='a', y='b'
[x, y = 'b'] = ['a', undefined]; // x='a', y='b'
var [x = 1] = [null] //x = null

对象的解构赋值
解构赋值还可以用于对象
var {foo, bar} = {foo: 'aaa', bar: 'bbb'};
// foo = 'aaa', bar = 'bbb'
对象的解构与数组有一个重要的不同。数组的元素是按次序排列的，变量的取值由它的位置决定；而对象的属性没有次序，变量必须与属性同名，才能取到正确的值，如：
var {foo, bar} = {bar:'aaa', foo: 'bbb'};
//foo = "bbb", bar='aaa'
对象的解构赋值的内部机制，是先找到同名属性，然后再赋给对应的变量。真正被赋值的是后者，而不是前者。
var {foo: baz} = {foo:'aaa', bar:'bbb'}
//baz = 'aaa' //foo  error, foo is not defined
//类似var { foo: foo, bar: bar } = { foo: "aaa", bar: "bbb" };
变量的声明和赋值是一体的
对于let和const来说，变量不能重新声明，所以一旦赋值的变量以前声明过，就会报错。
let foo;
let {foo} = {foo:1} //erro, duplicate declaration of foo
上面代码中，解构赋值的变量都会重新声明，所以报错了。不过，因为var命令允许重新声明，所以这个错误只会在使用let和const命令时出现。如果没有第二个let命令，上面的代码就不会报错。
let foo;
({foo} = {foo:1}) //ok
//允许嵌套s
var obj = {
      p: [
        "Hello",
        {y: 'world'} 
      ]
    };
 var {p:[x, {y}]} = obj;
//对象的解构也可以指定默认值，默认值生效的条件是，对象的属性值严格等于undefined

字符串的解构赋值
const [a, b,c,d, e] = 'hello';//a ='h', ...
类似数组对象都有一个length
let {length : len} = 'hello';
len // 5
数值和布尔值得解构赋值
解构赋值时，如果等号右边是数值和布尔值，则会先转为对象。
let {toString: s} = 123;
s === Number.prototype.toString // true
let {toString: s} = true;
s === Boolean.prototype.toString // true
 
函数参数的解构赋值
function add([x,y]) {
  return x + y;
} 
var arr = [[1, 2], [3, 4]].map(([a, b]) => a + b);

函数的解构也可以使用默认值
function move ({x = 0, y = 0} = {}) {
  return [x ,y];
}
move({x: 3, y: 8});  //[3,8]
move({x: 3}); //[3,0]
move({}); //[0,0]
move(); // [0,0]

function move({x, y} = { x: 0, y: 0 }) {
  return [x, y];
}

move({x: 3, y: 8}); // [3, 8]
move({x: 3}); // [3, undefined]
move({}); // [undefined, undefined]
move(); // [0, 0]
上面代码是为函数move的参数指定默认值，而不是为变量x和y指定默认值，所以会得到与前一种写法不同的结果。

解构赋值用途
1、交换变量的值
[x, y] = [y, x]; 
2、 从函数返回多个值
// 返回一个数组
 
function example() {
  return [1, 2, 3];
}
var [a, b, c] = example();
 
// 返回一个对象
 
function example() {
  return {
    foo: 1,
    bar: 2
  };
}
var { foo, bar } = example();
3、 函数参数的定义
// 参数是一组有次序的值
function f([x, y, z]) { ... }
f([1, 2, 3])
// 参数是一组无次序的值
function f({x, y, z}) { ... }
f({z: 3, y: 2, x: 1})
4、 提取JSON数据
var jsonData = {
  id: 42,
  status: "OK",
  data: [867, 5309]
}
let { id, status, data: number } = jsonData;
 
console.log(id, status, number)
// 42, OK, [867, 5309]
 
5、 函数参数的默认值
jQuery.ajax = function (url, {
  async = true,
  beforeSend = function () {},
  cache = true,
  complete = function () {},
  crossDomain = false,
  global = true,
  // ... more config
}) {
  // ... do stuff
}; 
6、 遍历Map结构  
var map = new Map();
map.set('first', 'hello');
map.set('second', 'world');
 
for (let [key, value] of map) {
  console.log(key + " is " + value);
}
// first is hello
// second is world
 
如果只想获取键名，或者只想获取键值，可以写成下面这样。    
// 获取键名
for (let [key] of map) {
  // ...
}
 
// 获取键值
for (let [,value] of map) {
  // ...
}    
7、 输入模块的指定方法    
const { SourceMapConsumer, SourceNode } = require("source-map"); 

字符串的扩展
字符的Unicde表示法
codePointAt() //如果确实要处理字符
String.fromCodePoint()
字符串的遍历器接口
at();
'abc'.at(0) // "a"
'𠮷'.at(0) // "𠮷"
normalize()
includes(), startsWidth(),endsWith()
传统上，JavaScript只有indexOf方法，可以用来确定一个字符串是否包含在另一个字符串中。ES6又提供了三种新方法:
includes()：返回布尔值，表示是否找到了参数字符串。
startsWith()：返回布尔值，表示参数字符串是否在源字符串的头部。
endsWith()：返回布尔值，表示参数字符串是否在源字符串的尾部。
var s = 'Hello world!';

s.startsWith('Hello') // true
s.endsWith('!') // true
s.includes('o') // true
//第二个参数表示搜索位置
var s = 'Hello world!';
s.startsWith('world', 6) // true
s.endsWith('Hello', 5) // true
s.includes('Hello', 6) // false
repeat()
repeat方法返回一个新字符串，表示将原字符串重复n次。

es7提供补齐padStart(), padEnd()
'x'.padStart(5, 'ab').// 'ababx'
'x'.padEnd(4, 'ab').// 'xabab'

模板字符串
标签模板、实例模板：暂不讨论

String.raw();

参考文献:
https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Text_formatting
trim
repeat
normalize
toLowerCase, toUpperCase
match,replace,search
substring,substr
slice
split
contact
fromCharCode,fromCodePoint
startsWith,endsWith,includes
indexOf,lastIndexOf
charAt,charCodeAt,codePointAt

正则扩展
RegExp构造函数
var regex = new RegExp('xyz', 'i');
//等价
var regex = /xyz/i
或者
var regex = new RegExp(/xyz/i);
=> var regex = /xyz/i
es6:
new RegExp(/abc/ig, 'i').flags //'i'

字符串的正则方式：
字符串对象共有4个方法，可以使用正则表达式：match()、replace()、search()和split()。

正则匹配难度比较大，暂时不讨论

数值类型
二进制和八进制的表示
ES6提供了二进制和八进制数值的新的写法，分别用前缀0b（或0B）和0o（或0O）表示。
0b111110111 === 503 // true
0o767 === 503 // true
Number.isFinite() , NumberisNaN()
ES6在Number对象上，新提供了Number.isFinite()和Number.isNaN()两个方法，用来检查Infinite和NaN这两个特殊值。
Number.isFinite()用来检查一个数值是否非无穷（infinity）。
Number.isFinite(15); // true
Number.isFinite(0.8); // true
Number.isFinite(NaN); // false
Number.isFinite(Infinity); // false
Number.isFinite(-Infinity); // false
Number.isFinite('foo'); // false
Number.isFinite('15'); // false
Number.isFinite(true); // false
Number.isNaN()用来检查一个值是否为NaN。
它们与传统的全局方法isFinite()和isNaN()的区别在于，传统方法先调用Number()将非数值的值转为数值，再进行判断，而这两个新方法只对数值有效，非数值一律返回false。

Number.parseInt(), Number.parseFloat()
// ES5的写法
parseInt('12.34') // 12
parseFloat('123.45#') // 123.45

// ES6的写法
Number.parseInt('12.34') // 12
Number.parseFloat('123.45#') // 123.45

Number.isInteger()
Number.isInteger()用来判断一个值是否为整数。
Number.isInteger(25) // true
Number.isInteger(25.0) // true //js中25和25.0采用同样的存储方式
Number.isInteger(25.1) // false 
Number.isInteger("15") // false
Number.isInteger(true) // false

//js中这样部署 Number.isInteger();
(function (global) {
  var floor = Math.floor,
    isFinite = global.isFinite;

  Object.defineProperty(Number, 'isInteger', {
    value: function isInteger(value) {
      return typeof value === 'number' && isFinite(value) &&
        value > -9007199254740992 && value < 9007199254740992 &&
        floor(value) === value;
    },
    configurable: true,
    enumerable: false,
    writable: true
  });
})(this);

ES6在Number对象上面，新增一个极小的常量Number.EPSILON。
Number.EPSILON
// 2.220446049250313e-16
Number.EPSILON.toFixed(20)
// '0.00000000000000022204'

//JavaScript能够准确表示的整数范围在-2^53到2^53之间（不含两个端点），超过这个范围，无法精确表示这个值。
Number.MAX_SAFE_INTEGER和Number.MIN_SAFE_INTEGER
Number.isSafeInteger()则是用来判断一个整数是否落在这个范围之内

Math对象的扩展
Math.trunc() 、 Math.sign() 、Math.cbrt() 、Math.clz32
Math.imul()、Math.fround()、Math.hypot()、
对数方法
Math.expm1()//Math.expm1(x)返回ex - 1，
Math.log1p()、Math.log10()、Math.log2()
三角方法
指数运算符
let a = 2;
a **= 2;
// 等同于 a = a * a;

let b = 3;
b **= 3;
// 等同于 b = b * b * b;

参考文献：
https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Numbers_and_dates
数学对象Math
Math.PI Math.sin(1.34)
日期对象
处理日期时间的Date对象方法可分为以下几类：

"set" 方法, 用于设置Date对象的日期和时间的值。
"get" 方法,用于获取Date对象的日期和时间的值。
"to" 方法,用于返回Date对象的字符串格式的值。
parse 和UTC 方法, 用于解析Date字符串。

数字时钟
function JSClock() {
  var time = new Date();
  var hour = time.getHours();
  var minute = time.getMinutes();
  var second = time.getSeconds();
  var temp = "" + ((hour > 12) ? hour - 12 : hour);
  if (hour == 0)
    temp = "12";
  temp += ((minute < 10) ? ":0" : ":") + minute;
  temp += ((second < 10) ? ":0" : ":") + second;
  temp += (hour >= 12) ? " P.M." : " A.M.";
  return temp;
}

数组的扩展
扩展运算符 rest 参数的逆运算，将一个数组转为用逗号分隔的参数序列。
console.log(...[1, 2, 3])
// 1 2 3
console.log(1, ...[2, 3, 4], 5)
// 1 2 3 4 5
[...document.querySelectorAll('div')]
// [<div>, <div>, <div>]
复制数组
合并数组
与解构赋值结合
字符串
实现了 Iterator 接口的对象
Map 和 Set 结构，Generator 函数

Array.from() //将类似数组的对象转成真正的数组
let arrayLike = {
  '0': 'a',
  '1': 'b',
  '2': 'c',
  length: 3,
};
// ES5的写法
var arr1 = [].slice.call(arrayLike); // ['a', 'b', 'c']

// ES6的写法
let arr2 = Array.from(arrayLike); // ['a', 'b', 'c']
Array.from('hello') ;// ['h', 'e'...];

Array.from(arrayLike, x => x * x);
// 等同于
Array.from(arrayLike).map(x => x * x);
Array.from([1, 2, 3], (x) => x * x)
// [1, 4, 9]

Array.of方法用于将一组值，转换为数组。
Array.of(3,11,8) //[3， 11，8];

copyWithin()
数组实例的copyWithin方法，在当前数组内部，将指定位置的成员复制到其他位置（会覆盖原有成员），然后返回当前数组。target、start、end三个参数
[1, 2, 3, 4, 5].copyWithin(0, 3)// [4, 5, 3, 4, 5]

find的()和findIndex//数组实例的find方法，用于找出第一个符合条件的数组成员
[1, 4, -5, 10].find((n) => n < 0)// -5
[1, 5, 10, 15].findIndex(function(value, index, arr) {
  return value > 9;
}) // 2
fill方法使用给定值，填充一个数组。
['a', 'b', 'c'].fill(7)
// [7, 7, 7]
new Array(3).fill(7)
// [7, 7, 7]
fill方法还可以接受第二个和第三个参数，用于指定填充的起始位置和结束位置。
['a', 'b', 'c'].fill(7, 1, 2);// ['a', 7, 'c']
数组实例的entries(), keys(), values()

参考文献：
https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Indexed_collections
var arr = new Array(element0, element1, ..., elementN);
var arr = Array(element0, element1, ..., elementN);
var arr = [element0, element1, ..., elementN];
//创建和填充数组
var emp = [];
emp[0] = "Casey Jones";
emp[1] = "Phil Lesh";
emp[2] = "August West";
引用数组元素
遍历数组
数组方法
contact
var myArray = new Array("1", "2", "3");
myArray = myArray.concat("a", "b", "c"); 

joint 将数组的所有元素连接成一个字符串。
var myArray = new Array("Wind", "Rain", "Fire");
var list = myArray.join(" - "); // list is "Wind - Rain - Fire"

push 在数组末尾添加一个或多个元素，并返回数组操作后的长度。
var myArray = new Array("1", "2");
myArray.push("3"); // myArray is now ["1", "2", "3"]

pop()

shift() 移除数组第一个元素

unshift()

slice从数组提取一个片段，并作为一个新数组返回

reverse() 颠倒数组元素的顺序：第一个变成最后一个，最后一个变成第一个。

sort() 给数组元素排序。

indexOf(searchElement[, fromIndex]) 在数组中搜索searchElement 并返回第一个匹配的索引。

lastIndexOf(searchElement[, fromIndex]) 和 indexOf 差不多，但这是从结尾开始，并且是反向搜索。

forEach(callback[, thisObject]) 在数组每个元素项上执行callback

map(callback[, thisObject]) 在数组的每个单元项上执行callback函数，并把返回包含回调函数返回值的新数组（译者注：也就是遍历数组，并通过callback对数组元素进行操作，并将所有操作结果放入数组中并返回该数组）

filter(callback[, thisObject]) 返回一个包含所有在回调函数上返回为true的元素的新数组（译者注：callback在这里担任的是过滤器的角色，当元素符合条件，过滤
器就返回true，而filter则会返回所有符合过滤条件的元素）。

every(callback[, thisObject]) 当数组中每一个元素在callback上被返回true时就返回true（译者注：同上，every其实类似filter，只不过它的功能是判断是不是数组中的所有元素都符合条件，并且返回的是布尔值）。

some(callback[, thisObject]) 只要数组中有一项在callback上被返回true，就返回true（译者注：同上，类似every，不过前者要求都符合筛选条件才返回true，后者只要有符合条件的就返回true

reduce(callback[, initialValue]) 使用回调函数 callback(firstValue, secondValue) 把数组列表计算成一个单一值（译者注：他数组元素两两递归处理的方式把数组计算成一个值）
var a = [10, 20, 30];
var total = a.reduce(function(first, second) { return first + second; }, 0);
console.log(total) // Prints 60

多维数组
var a = new Array(4);
for (i = 0; i < 4; i++) {
  a[i] = new Array(4);
  for (j = 0; j < 4; j++) {
    a[i][j] = "[" + i + "," + j + "]";
  }
}

函数的扩展
javascript中函数就是对象。对象是键值对的集合并拥有一个连接到原型对象的隐形连接,对象连接到Object.prototype，函数连接到Function.prototype.
函数是对象。
函数字面量：保留字function 、函数名（可省略，用于递归）、参数、执行域
//ES6函数默认值
var add = function(a, b = 0) {
  return a+b;
}
//与解构赋值默认值结合使用
function foo({x, y = 5}) {
  console.log(x, y);
}
foo({}) // undefined 5
//函数length属性
指定了默认值以后，函数的length属性，将返回没有指定默认值的参数个数
//作用域，指定函数参数
function throwIfMissing() {
  throw new Error('Missing parameter');
}

function foo(mustBeProvided = throwIfMissing()) {
  return mustBeProvided;
}
foo()
// Error: Missing parameter
//rest参数
function push(array, ...items) {
  items.forEach(function(item) {
    array.push(item);
    console.log(item);
  });
}
var a = [];
push(a, 1, 2, 3)
//name属性
var f = function () {};
// ES5
f.name // ""
// ES6
f.name // "f"

//箭头函数
var sum = (c, d) => {return c+d};
方法调用模式:当一个函数是一个对象的属性时
var myObject = {
  value: 0,
  increment: function (inc) {
    this.value += typeof inc === 'number' ? inc : 1;
  }
};
myObject.increment(); 
alert(myObject.value);// 1;
函数调用模式：当一个函数并非一个对象的属性时。
当函数以此模式调用时，this被绑定到全局对象。这是语言设计上的一个错误。正确的设计应该是当内部函数被调用时，this应该仍然绑定到外部函数的this变量。
var sum = add(3,4);
//解决的办法是：如果该方法定义一个变量并给它赋值this,那么内部函数就可以通过这个变量访问到外部函数的this.
//给myObject增加一个double方法。
myObject.double = function () {
  var that = this;//如果不这么赋值会发生意想不到的错误，内部函数无法访问到外部的this,内部函数访问的是全局的this,就有bug.
  var helper = function () {
  that.value = add(that.value, that.value);
 }
  helper();//以函数形式调用helper.
};
myOjbect.double(); //myOjbect.value = 2, 否则是1.

构造器调用模式：
var Quo = function (string) {//创建一个Quo名的构造器函数。并构造一个带有status属性的对象。
    this.status = string;
 } 
Quo.prototype.get_status = function() {//给Quo的所有实例提供一个方法。
     return this.status;
};
var myQuo = new Quo("confused"); //new 构造一个Quo实例
alert(myQuo.get_status());

Apply调用模式
javascript是函数式的面向对象的语言，所以函数可以拥有方法。
apply方法让我们构建一个参数数组并用其去调用函数，apply方法接收两个参数，一个是将被绑定给this的值，第二个是参数数组。
var array = [3, 5];
var sum = add.apply(null, array);//sum = 8
var statusObject = {
  status: 'A-OK',
};
var status = Quo.prototype.get_status.apply(statusObject); //status : 'A-OK'

函数参数：arguments数组是默认的。
返回值：
异常：

给函数添加方法：Function.prototype.method = function() {}

递归：


参考文献：https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Functions
值传递和引用传递 ---- 函数重要知识点
function map (f, a) {
    var result = [];
    for (let i = 0; i < a.length; i++) {
        result[i] = f(a[i]);
    }
    return result;
}

var f = function(x) {
    return x*x*x;
}

var numbers = [0,1,2,5,10];
var cube = map(f,numbers);
console.log(cube);
for(let value  in numbers) {
    console.log(numbers[value]);
}

函数作用域
递归
嵌套函数和闭包
闭包
函数参数
箭头函数
this


ES6函数

箭头函数：
var f = v => v， 等同于： var f = function(v) {return v;};
var geetTmpItem = id => ({id:id, name: 'Tmp'});//返回对象时，用圆括号括起来
const full = ({first, last}) => first + '' + last;//变量解构
var sum = (num1, num2) => { return num1 + num2; }

对象
//null表示没有对象，即该处不应该有值
（1） 作为函数的参数，表示该函数的参数不是对象。
（2） 作为对象原型链的终点。
Object.getPrototypeOf(Object.prototype)// null

//undefined表示"缺少值"，就是此处应该有一个值，但是还没有定义
（1）变量被声明了，但没有赋值时，就等于undefined。
（2) 调用函数时，应该提供的参数没有提供，该参数等于undefined。
（3）对象没有赋值的属性，该属性的值为undefined。
（4）函数没有返回值时，默认返回undefined。
var i;
i // undefined
function f(x){console.log(x)}
f() // undefined
var  o = new Object();
o.p // undefined
var x = f();
x // undefined

对象有时也被叫作关联数组
var myCar = new Object();
myCar.make = "Ford"
或者
myCar["model"] = "Mustang";

//枚举属性
function showProps(obj,objName) {
    var result = "";
    for(var i in obj) {
        if (obj.hasOwnProperty(i)) {
            result += objName + "." + i + "=" + obj[i] + "\n";
        }
    }
    return result;
}

var myCard = new Object();
myCard.make = "Ford";
myCard.model = "Mystang";
myCard.year = 1969;
console.log(showProps(myCard, "myCard"))

Object.keys(o)
Object.getOwnPropertyNames(o)
//使用对象初始化器初始化一个对象
var obj = { property_1:   value_1,   // property_# 可以是一个标识符...
            2:            value_2,   // 或一个数字...
           ["property" +3]: value_3,  //  或一个可计算的key名... 
            // ...,
            "property n": value_n }; // 或一个字符串
//使用构造函数初始化对象
function Car(make, model, year) {
    this.make = make ;
    this.model = model;
    this.year = year;
}
var mycard_1 = new Car("eagle", "talon",1993)

//使用Object.create方法
//为对象类型定义属性，其中Car为构造函数
Car.prototype.color = null;
car1.color = "black";

//定义方法
objectName.methodname = function_name;

var myObj = {
  myMethod: function(params) {
    // ...do something
  }
  // 或者 这样写也可以  
  myOtherMethod(params) {
    // ...do something else
  }
};

get 和 set方法
删除属性
比较对象

ES6对象方法简写
let birth = '2000/01/01';
const Person = {
  name: '张三',
  //等同于birth: birth
  birth,
  // 等同于hello: function ()...
  hello() { console.log('我的名字是', this.name); }
};

Object.is()
Object.assign() 浅拷贝、同名属性替换、数组处理、取值函数的处理
1）给对象添加属性
class Point {
  constructor(x, y) {
    Object.assign(this, {x, y});
  }
}
Object.assign(SomeClass.prototype, {
  someMethod(arg1, arg2) {
    ···
  },
  anotherMethod() {
    ···
  }
});
// 等同于下面的写法
SomeClass.prototype.someMethod = function (arg1, arg2) {
  ···
};
SomeClass.prototype.anotherMethod = function () {
  ···
};
3）克隆对象
4）合并多个对象

//属性的可枚举性和遍历
let obj = { foo: 123 };
Object.getOwnPropertyDescriptor(obj, 'foo')
属性的遍历

//__proto__属性，Object.setPrototypeOf()，Object.getPrototypeOf() 
// es6 的写法
const obj = {
  method: function() { ... }
};
obj.__proto__ = someOtherObj;

// es5 的写法
var obj = Object.create(someOtherObj);
obj.method = function() { ... };

//super关键字

//Object.keys()，Object.values()，Object.entries()

//对象的扩展运算符
let z = { a: 3, b: 4 };
let n = { ...z };
n // { a: 3, b: 4 }


Class类
1.ES5写法
function Point(x, y) {
    this.x = x;
    this.y = y;
}
Point.prototype.toString = function() {
    return '(' + this.x + ',' + this.y + ')';
};
console.log(Point.prototype);[ 'toString' ]

2.ES6写法
class Point {
    constructor(x, y) {//默认方法
        this.x = x;
        this.y = y;
    }
    toString() {
        return '(' + this.x + ',' + this.y + ')';
    }
    get prop () {//定义getter和setter函数
        return 'shit-get';
    }
    set prop(value) {
        console.log('setter'+value);
    }
    static classMethod() {//静态方法
        return 'Hello, world';
    }
}
var point = new Point(8,0);
console.log(point.toString());//(8.0)
console.log(typeof point);//object
console.log(typeof Point);//function
console.log(Point.classMethod());//调用静态方法
类的所有方法都定义在类的prototype属性上面,在类的实例上面调用方法，其实就是调用原型上的方法,如下
point.constructor = Ponit.prototype.constructor//true

3.类的内部所有定义的方法，都是不可枚举的（non-enumerable),这与ES5不一致。
console.log(Point.prototype);// Point{}
console.log(Object.getOwnPropertyNames(Point.prototype));//[ 'constructor', 'toString' ]
console.log(point.hasOwnProperty('x'));//true
console.log(point.hasOwnProperty('toString'));//false
console.log(point.__proto__.hasOwnProperty('toString'));//true
4.同ES5,类的所有实例共享一个原型对象
point1.__proto__ = point2.__proto__
可以通过__proto__为Class添加方法。
point.__proto__.printName = function(){};
//同
Point.prototype.printName = function(){};

以上更改类慎用

5.class继承
class ColorPoint extends Point{}
子类必须在constructor方法中调用super方法，否则新建实例会报错。

6.类的prototype和__proto__
（1）子类的__proto__属性，表示构造函数的继承，总是指向父类。
（2）子类prototype属性的__proto__属性，表示方法的继承，总是指向父类的prototype属性。
class A{} class B extends A{}
B.__proto__ === A;//true
B.prototype.__proto__ === A.prototype;//true
Object.getPrototypeOf方法可以用来从子类上获取父类:
Object.getPrototypeOf(B) == A//true

7.super关键字
super这个关键字，有两种用法，含义不同。
（1）作为函数调用时（即super(...args)），super代表父类的构造函数。
（2）作为对象调用时（即super.prop或super.method()），super代表父类。注意，此时super既可以引用父类实例的属性和方法，也可以引用父类的静态方法。

子类继承父类，必须调用super，且需要在this前调用

8.实例的__proto__属性
子类实例的__proto__属性的__proto__属性，指向父类实例的__proto__属性。也就是说，子类的原型的原型，是父类的原型。
因此，通过子类实例的__proto__.__proto__属性，可以修改父类实例的行为。

9.ES6允许原生构造函数的继承
class MyArray extends Array {
  constructor(...args) {
    super(...args);
  }
}
但是es5是不能够直接继承原生构造函数的。
Boolean()/Number()/String()/Array()/Date()/Function()/RegExp()/Error/Object()

9.Class的getter、setter
写法见上2。

10.class的generator函数
class Foo {
    constructor(...args) {
        this.args = args;
    }
    * [Symbol.iterator]() {
        for (let arg of this.args) {
            yield arg;
        }
    }
}
for (let x of new Foo('hello', 'world')) {
    console.log(x);
}
如果某个方法之前加上星号（*），就表示该方法是一个Generator函数。
Symbol.iterator方法返回一个Foo类的默认遍历器，for...of循环会自动调用这个遍历器.

11.Class的静态方法
类相当于实例的原型，所有在类中定义的方法，都会被实例继承。
如果在一个方法前，加上static关键字，就表示该方法不会被实例继承，而是直接通过类来调用，这就称为“静态方法”。
代码见上2。
父类静态方法可以被子类继承，且可以从super对象调用。

12.Class静态属性和实例属性
class Foo {
}
Foo.prop = 1;
Foo.prop // 1
只有之中方法定义可行。es6类内部不能定义静态属性。
目前，es6的实例属性也只能定义在方法或者constructor方法里。es7允许。

13.newTarget属性
14.Mixin模式
Mixin模式指的是，将多个类的接口“混入”（mix in）另一个类。它在ES6的实现如下。
class DistributedEdit extends mix(Loggable, Serializable) {
  // ...
}

15.Object.getPrototypeOf方法可以用来从子类上获取父类。

Iterator和 for…of循环

遍历器（Iterator）就是这样一种机制。它是一种接口，为各种不同的数据结构提供统一的访问机制。任何数据结构只要部署 Iterator 接口，就可以完成遍历操作（即依次处理该数据结构的所有成员）。



Promise对象
1.Promise含义、基本用法
var promise = new Promise(function(resolve, reject) {
    console.log('fuck');
    var shit = 'g';
    if ('st') {
        resolve('shit');
    }else {
        reject('go');
    }
});
console.log(promise);
promise.then(function(value) {//使用、success、resolved
    console.log('we did it.');
}, function(error) {//failure、rejected
});
Promise对象三种状态：Pending、Resolved、Rejected
then方法可以接受两个回调函数作为参数。第一个回调函数是Promise对象的状态变为Resolved时调用，第二个回调函数是Promise对象的状态变为Reject时调用。其中，第二个函数是可选的，不一定要提供。这两个函数都接受Promise对象传出的值作为参数。
console.log(Object.getOwnPropertyNames(promise.__proto__));
//[ 'constructor', 'chain', 'then', 'catch' ]

2.Promise对象实例
var getJSON = function(url) {
  var promise = new Promise(function(resolve, reject){
    var client = new XMLHttpRequest();
    client.open("GET", url);
    client.onreadystatechange = handler;
    client.responseType = "json";
    client.setRequestHeader("Accept", "application/json");
    client.send();

    function handler() {
      if (this.readyState !== 4) {
        return;
      }
      if (this.status === 200) {
        resolve(this.response);
      } else {
        reject(new Error(this.statusText));
      }
    };
  });

  return promise;
};

getJSON("/posts.json").then(function(json) {
  console.log('Contents: ' + json);
}, function(error) {
  console.error('出错了', error);
});

3.Promise.prototype.then()
console.log(Object.getOwnPropertyNames(promise.__proto__));//[ 'constructor', 'chain', 'then', 'catch' ]
then方法的第一个参数是Resolved状态的回调函数，第二个参数（可选）是Rejected状态的回调函数。
then方法返回的是一个新的Promise实例（注意，不是原来那个Promise实例）。因此可以采用链式写法，即then方法后面再调用另一个then方法。
getJSON("/posts.json").then(function(json) {
  return json.post;
}).then(function(post) {
  //...
});
面的代码使用then方法，依次指定了两个回调函数。第一个回调函数完成以后，会将返回结果作为参数，传入第二个回调函数。

4.Promise.prototype.catch()
Promise.prototype.catch方法是.then(null, rejection)的别名，用于指定发生错误时的回调函数。
getJSON("/posts.json").then(function(posts) {
  //...
}).catch(function(error) {
    // 处理 getJSON 和 前一个回调函数运行时发生的错误
  console.log('发生错误！', error);
});//如果状态变为Rejected则会调用catch方法指定回调函数。处理错误。

5.Promise.all()
用于将多个Promise实例包装成一个新的Promise实例。只要数组中其中一个状态被reject,则返回一个reject实例。
var promises = [1,3,4,5,90,8].map(function(id) {
  return getJSON("/post/" + id + ".json");
});
Promise.all(promises).then(function(post){
//...
}).catch(function(reason){
  /...
});

6.Promise.race()
同上、方法
7.Promise.resolve()
该方法将现有对象转化为Promise对象。
Promise.resolve('foo')
//等价于
new Promise(resolve => resolve('foo'));
8.Promise.reject()
Promise.reject(reason)方法也会返回一个新的Promise实例，该实例的状态为rejected。用法与上面一致
var p = Promise.reject('出错了');
=> var p = new  Promise((resolve, reject) => reject('出错了'))；
p.then(null, function(s) {
  console.log(s);
});//出错了
9.done()和finally()

Promise对象的回调链，不管以then方法或catch方法结尾，要是最后一个方法抛出错误，都有可能无法捕捉到（因为Promise内部的错误不会冒泡到全局）。因此，我们可以提供一个done方法，总是处于回调链的尾端，保证抛出任何可能出现的错误.
10.应用
const preloadImage = function (path) {
  return new Promise(function (resolve, reject) {
    var image = new Image();
    image.onload  = resolve;
    image.onerror = reject;
    image.src = path;
  });
};
async函数与Promise、Generator函数一样，是用来取代回调函数、解决异步操作的一种方法。它本质上是Generator函数的语法糖。async函数并不属于ES6，而是被列入了ES7，但是traceur、Babel.js、regenerator等转码器已经支持这个功能，转码后立刻就能使用。

Set和Map结构
1.Set,不会重复添加元素
var s = new Set();
[1,2,1,5,5,8,6,2,7].map(x=>s.add(x));
for(let i of s){log(i)}//1,2,5,6,7,8
2.常用操作
var set = new Set([1,2,3,4,4]);
[...set];//[1,2,3,4]
set.size; 4
[...new Set(array)];//去除数组重复成员
向Set加入值的时候，不会发生类型转换，5和'5'不同，NaN等于自身
两个对象总是不等：set.add({}); set.size =1,set.add({}),set.size=2;

2.属性和方法
属性：constructor、size
方法：操作方法和遍历方法
get(key);
set(key,value);
add(value)
delete(value)
has(value)
clear()
Array.from(set)=>array
keys();
values();
entries();
forEach();set.forEach((value, key)=>console.log(value*2));
扩展运算符内部用for...of循环，所以也可以用于Set结构,数组的map和filter方法也可以用于Set了。
let a = new Set([1, 2, 3]);
let b = new Set([4, 3, 2]);
// 并集
let union = new Set([...a, ...b]);
// [1, 2, 3, 4]
// 交集
let intersect = new Set([...a].filter(x => b.has(x)));
// [2, 3]
// 差集
let difference = new Set([...a].filter(x => !b.has(x)));
// [1]
3.WeakSet
4.Map
JavaScript的对象（Object），本质上是键值对的集合（Hash结构），但是只能用字符串当作键。这给它的使用带来了很大的限制.
Map也是键值对，但是键的范围不限于字符串，各种类型的值都可以当做对象。
var m = new Map();
var o = {p: 'Hello world'};
m.set(o, 'content');
m.get(o);//"content"
m.has(o)//true
m.delete(o)//true
m.has(o)//false
var map = new Map([['name', '张三'], ['title', 'Author']]);//接受数组做参数
3.与其他类型的互相转化
let myMap = new Map().set(true, 7).set({foo: 3}, ['abc']);
[...myMap]；// [ [ true, 7 ], [ { foo: 3 }, [ 'abc' ] ] ]
转为对象：
function strMapToObj(strMap) {
  let obj = Object.create(null);
  for (let [k,v] of strMap) {
    obj[k] = v;
  }
  return obj;
}


Module
1.前言
JavaScript语言一直没有分模块的东西，社区解决方案是CommonJS和AMD两种。
静态优化、运行时加载。
es5、CommonJS模块
let {stat, exits, readFile } = require('fs');
上述代码中实质上是整体加载fs模块生成一个对象，然后从对象中读取三个方法。为运行时加载。
es6、Module
import {stat, exits, readFile} from 'fs';
上述代码的实质是从fs中加载3个方法，其他方法不加载，为编译时加载。

2.use strict
严格模式主要有以下限制。

变量必须声明后再使用
函数的参数不能有同名属性，否则报错
不能使用with语句
不能对只读属性赋值，否则报错
不能使用前缀0表示八进制数，否则报错
不能删除不可删除的属性，否则报错
不能删除变量delete prop，会报错，只能删除属性delete global[prop]
eval不会在它的外层作用域引入变量
eval和arguments不能被重新赋值
arguments不会自动反映函数参数的变化
不能使用arguments.callee
不能使用arguments.caller
禁止this指向全局对象
不能使用fn.caller和fn.arguments获取函数调用的堆栈
增加了保留字（比如protected、static和interface）

3.export命令
export 可输出函数、类、变量
export var firstName = 'Mike';
export default Home;
export {firstName, lastName, year};
export function mutiply(x, y) {
  return x * y;
}
export {f};//f为function
通常情况下，export输出的变量就是本来的名字，但是可以使用as关键字重命名。
function v1(){...}
export {v1 as streanV1};
另外，export语句输出的接口，与其对应的值是动态绑定关系，即通过该接口，可以取到模块内部实时的值。
export var foo = 'bar';
setTimeout(() => foo = 'baz', 500);上面代码输出变量foo，值为bar，500毫秒之后变成baz

4.import
import {firstName, lastName, year} from './profile';
import {lastName as surname} from './profile';//使用as关键字重命名

5.模块的整体加载
//circel.js
export function area(){}
export function name(){}
//main.js
import {area, name} from './circle'
整体加载：使用 * as关键字
import * as circle from './circle'
console.log(circle.area);

6.export default命令
为了给用户提供方便，让他们不用阅读文档就能加载模块，就要用到export default命令，为模块指定默认输出。
export default function() {log('foo')}; //export_default.js
import  customname from './export_default'
 customName();//'foo'
 
7.模块的继承


Generator函数
1.属性
Generator函数有多种理解角度。从语法上，首先可以把它理解成，Generator函数是一个状态机，封装了多个内部状态。
执行Generator函数会返回一个遍历器对象，也就是说，Generator函数除了状态机，还是一个遍历器对象生成函数。返回的遍历器对象，可以依次遍历Generator函数内部的每一个状态。
function* helloworldGenerator() {
    yield 'hello';
    yield 'world';
    return 'ending';
}
var hw = helloworldGenerator();
hw.next();//hello,done
hw.next();//world;
hw.next();//ending
hw.next();//undefined
2.for...of循环
for(let v of helloworldGenerator()) {
  console.log(v);//1 2 3 4 5
}


webpack入门

参考文献：https://segmentfault.com/a/1190000006178770#articleHeader3c
1、webpack作用
WebPack可以看做是模块打包机：它做的事情是，分析你的项目结构，找到JavaScript模块以及其它的一些浏览器不能直接运行的拓展语言（Scss，TypeScript等），并将其转换和打包为合适的格式供浏览器使用

2、webpack安装
//全局安装
npm install -g webpack
//安装到你的项目目录
npm install --save-dev webpack

3、正式使用
在项目根目录创建package.json 文件 或者 在终端通过npm init创建pakage.json

4、创建app和public文件夹

5、正式使用webpack
# {extry file}出填写入口文件的路径，本文中就是上述main.js的路径，
# {destination for bundled file}处填写打包文件的存放路径
# 填写路径的时候不用添加{}
webpack {entry file} {destination for bundled file}
# webpack非全局安装的情况
node_modules/.bin/webpack app/main.js public/bundle.js

6、通过配置文件使用webpack
在项目根目录下创建webpack.config.js
module.exports = {
  entry:  __dirname + "/app/main.js",//已多次提及的唯一入口文件
  output: {
    path: __dirname + "/public",//打包后的文件存放的地方
    filename: "bundle.js"//打包后输出文件的文件名
  }
}

7、更快捷打包方式
{
  "name": "lib",
  "version": "1.0.0",
  "description": "",
  "main": "main.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "dev": "webpack",
    "server": "webpack-dev-server --open"
  },
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "webpack": "^3.11.0"
  }
}

8、使用webpack构建本地服务器
全局安装
npm install -g webpack-dev-server
在终端输入npm run server 即可打开浏览器查看结果

9、Loaders
10、Babel安装和配置
# npm一次性安装多个依赖模块，模块之间用空格隔开.非全局安装
npm install --save-dev babel-core babel-loader babel-preset-env babel-preset-react

#npm install --save react react-dom
npm install --save react react-dom

Babel其实可以完全在 webpack.config.js 中进行配置，但是考虑到babel具有非常多的配置选项，在单一的webpack.config.js文件中进行配置往往使得这个文件显得太复杂，因此一些开发者支持把babel的配置选项放在一个单独的名为 ".babelrc" 的配置文件中。我们现在的babel的配置并不算复杂，不过之后我们会再加一些东西，因此现在我们就提取出相关部分，分两个配置文件进行配置（webpack会自动调用.babelrc里的babel配置选项）

11、一切皆模块
webpack提供两个工具处理样式表，css-loader 和 style-loader，二者处理的任务不同，css-loader使你能够使用类似 @import 和 url(...)的方法实现 require()的功能,style-loader将所有的计算后的样式加入页面中，二者组合在一起使你能够把样式表嵌入webpack打包后的JS文件中。

12、CSS module
被称为CSS modules的技术意在把JS的模块化思想带入CSS中来，通过CSS模块，所有的类名，动画名默认都只作用于当前模块。Webpack对CSS模块化提供了非常好的支持，只需要在CSS loader中进行简单配置即可，然后就可以直接把CSS的类名传递到组件的代码中，这样做有效避免了全局污染

module.exports = {

    ...

    module: {
        rules: [
            {
                test: /(\.jsx|\.js)$/,
                use: {
                    loader: "babel-loader"
                },
                exclude: /node_modules/
            },
            {
                test: /\.css$/,
                use: [
                    {
                        loader: "style-loader"
                    }, {
                        loader: "css-loader",
                        options: {
                            modules: true, // 指定启用css modules
                            localIdentName: '[name]__[local]--[hash:base64:5]' // 指定css的类名格式
                        }
                    }
                ]
            }
        ]
    }
};

作者：采香行处蹙连钱
链接：https://www.jianshu.com/p/31e555ec64b5
來源：简书
简书著作权归作者所有，任何形式的转载都请联系作者获得授权并注明出处。
