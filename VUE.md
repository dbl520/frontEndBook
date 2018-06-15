# GitBook

# VUE
```
  // 命名路由，append 属性，查询参数，router-link渲染成<li>标签
<router-link tag="li" :to="{name:'demandindex', append:true,  query: {isFormBackend: 1}, activeClass: 'bottom-nav-active'}">
</router-link>

// to的值：字符串形式
<router-link to="banner.image_url" ></router-link>

// to的值：对象形式，拼接多个动态参数
<router-link :to="{path: '/my/modify?modify=fullname&val=' + profile.nickname}" ></router-link>

// to的值：对象形式
<router-link :to="{path: '/home'}">返回首页</router-link>

// to的值：对象形式，拼接动态参数
<router-link to="{path: '/backend/coupon_order_detail/' + product.order_id+'?order_status='+product.order_status}"></router-link>

// to的值：对象形式，带一个路径参数
<router-link :to="{path: '/detail/' + this.$route.params.id}" ></router-link>

作者：汤利利
链接：https://www.jianshu.com/p/4b833b23dc4a
來源：简书
简书著作权归作者所有，任何形式的转载都请联系作者获得授权并注明出处。
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
