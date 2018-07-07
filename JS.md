# GitBook

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
