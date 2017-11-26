# GitBook

# 前端心得体会方法技巧

---

**小程序图片预览，current是当前图片的src**

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
