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

# Promise 的构造函数

构造一个 Promise，最基本的用法如下：

    ```
       var promise = new Promise(function(resolve, reject) {

            if (...) {  // succeed

                resolve(result);

            } else {   // fails

                reject(Error(errMessage));

            }
        });
```
