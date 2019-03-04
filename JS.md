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
