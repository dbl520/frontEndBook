# GitBook
#获取今天明天后天
```
  GetDateStr(0);//今天
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
