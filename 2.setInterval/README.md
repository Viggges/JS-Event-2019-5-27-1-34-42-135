## 要求 
    
- 实现一个基础的计时器应用，点击开始按钮开始计时，点击结束按钮结束计时，并把计时的结果显示在上面的输入框中。

```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <title>定时器示例</title>
  </head>
  <body>
  
  <input type="text" id="result">
  
  <input type="button" value="开始" id="begin">
  <input type="button" value="结束" id="end">
  
  <script type="text/javascript">
      // write your code here
      // ......
    var h=0;
    var m=0;
    var s=0;
    var ms=0;
	  
	  var time=0;
	  var begin = document.getElementById("begin");
	 var end = document.getElementById("end");
	  function clock(){
	  
	  ms=ms+9;         //毫秒
     if(ms>=1000){
       ms=0;
       s=s+1;         //秒
     }
     if(s>=60){
       s=0;
       m=m+1;        //分钟
     }
     if(m>=60){
       m=0;
       h=h+1;        //小时
     }
     var str =toDub(h)+"时"+toDub(m)+"分"+toDub(s)+"秒"+toDubms(ms)+"毫秒";
     var mytime = document.getElementById("result");
     mytime.value = str;
	 }
	 
   begin.onclick=function(){  //开始
     time=setInterval(clock,9);
	 
   }
 
   end.onclick=function(){  //暂停
     clearInterval(time);
   }
   
   function toDub(n){  //补0操作
     if(n<10){
       return "0"+n;
     }
     else {
       return ""+n;
     }
   }
 
   function toDubms(n){  //给毫秒补0操作
     if(n<10){
       return "00"+n;
     }
     else {
       return "0"+n;
  }
}
 
  </script>
  </body>
  </html>
```
