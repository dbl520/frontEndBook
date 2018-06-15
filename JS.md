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
