# JavaScript

1. 为什么利用多个域名来存储网站资源会更有效？
> 1. CDN缓存更方便
> 2. 突破浏览器并发限制
> 3. 节约cookie带宽
> 4. 节约主域名的连接数，优化页面响应速度
> 5. 防止不必要的安全问题

2. 请描述一下cookies，sessionStorage和localStorage的区别？
> sessionStorage用于本地存储一个会话（session）中的数据，这些数据只有在同一个会话中的页面才能访问并且当会话结束后数据也随之销毁。因此sessionStorage不是一种持久化的本地存储，仅仅是会话级别的存储。而localStorage用于持久化的本地存储，除非主动删除数据，否则数据是永远不会过期的。
web storage和cookie的区别
> Web Storage的概念和cookie相似，区别是它是为了更大容量存储设计的。Cookie的大小是受限的，并且每次你请求一个新的页面的时候Cookie都会被发送过去，这样无形中浪费了带宽，另外cookie还需要指定作用域，不可以跨域调用。
除此之外，Web Storage拥有setItem,getItem,removeItem,clear等方法，不像cookie需要前端开发者自己封装setCookie，getCookie。但是Cookie也是不可以或缺的：Cookie的作用是与服务器进行交互，作为HTTP规范的一部分而存在 ，而Web Storage仅仅是为了在本地“存储”数据而生。

3. javascript的typeof返回哪些数据类型
> alert(typeof [1, 2]); //object
> alert(typeof 'leipeng'); //string
> var i = true; 
> alert(typeof i); //boolean
> alert(typeof 1); //number
> var a; 
> alert(typeof a); //undefined
> function a(){;};
> alert(typeof a) //function

4.	例举3种强制类型转换和2种隐式类型转换?
> 强制（parseInt(),parseFloat(),Number()）
> 隐式（== ,!!）

5.	split() 、join() 的区别
> 前者是切割成数组的形式，后者是将数组转换成字符串

6.	数组方法pop() push() unshift() shift()
> Push()尾部添加 pop()尾部删除
> Unshift()头部添加 shift()头部删除

7.	事件绑定和普通事件有什么区别
> 普通添加事件的方法不支持添加多个事件，最下面的事件会覆盖上面的，而事件绑定（addEventListener）方式添加事件可以添加多个。
> ddEventListener不兼容低版本IE
普通事件无法取消
> addEventLisntener还支持事件冒泡+事件捕获

8.	IE和DOM事件流的区别
> 1.执行顺序不一样
> 2.参数不一样
> 3.事件加不加on
> 4.this指向问题

9.	IE和标准下有哪些兼容性的写法
> var ev = ev || window.event
> document.documentElement.clientWidth || document.body.clientWidth
> var target = ev.srcElement||ev.target

8.	call和apply的区别
> call方法: 
> 语法：call(thisObj，Object1,Object2...)
> 定义：调用一个对象的一个方法，以另一个对象替换当前对象。
> 说明：
> call 方法可以用来代替另一个对象调用一个方法。call 方法可将一个函数的对象上下文从初始的上下文改变为由 thisObj 指定的新对象。 
> 如果没有提供 thisObj 参数，那么 Global 对象被用作 thisObj。 
> apply方法： 
> 语法：apply(thisObj，[argArray])
> 定义：应用某一对象的一个方法，用另一个对象替换当前对象。 
> 说明： 
> 如果 argArray 不是一个有效的数组或者不是 arguments 对象，那么将导致一个 TypeError。 
> 如果没有提供 argArray 和 thisObj 任何一个参数，那么 Global 对象将被用作 thisObj， 并且无法被传递任何参数。

9.	b继承a的方法
> function A( age, name ){ 
>   this.age = age; 
>   this.name = name; 
> } 
> 
> A.prototype.show = function(){ 
>   alert('父级方法'); 
> } 
> 
> function B(age,name,job){ 
>   A.apply( this, arguments ); 
>   this.job = job; 
> } 
> 
> B.prototype = new A();
> var b = new A(14,'侠客行'); 
> var a = new B(15,'狼侠','侠客'); 

10.	如何阻止事件冒泡和默认事件
> canceBubble()只支持IE,return false,stopPropagation()

11.	添加 删除 替换 插入到某个接点的方法
> obj.appendChid()
> obj.insertBefore()
> obj.replaceChild()
> obj.removeChild()

> 12.	javascript的本地对象，内置对象和宿主对象
> 本地对象为array obj regexp等可以new实例化
> 内置对象为gload Math 等不可以实例化的
> 宿主为浏览器自带的document,window 等

13.	window.onload 和document ready的区别
> window.onload 是在dom文档树加载完和所有文件加载完之后执行一个函数Document.ready原生种没有这个方法，jquery中有 $().ready(function),在dom文档树加载完之后执行一个函数（注意，这里面的文档树加载完不代表全部文件加载完）。
> $(document).ready要比window.onload先执行
> window.onload只能出来一次，$(document).ready可以出现多次

14.	”==”和“===”的不同
> 前者会自动转换类型
> 后者不会

15.	javascript的同源策略
> 一段脚本只能读取来自于同一来源的窗口和文档的属性，这里的同一来源指的是主机名、议和端口号的组合

16.	JavaScript是一门什么样的语言，它有哪些特点？
> javaScript一种直译式脚本语言，是一种动态类型、弱类型、基于原型的语言，内置支持类型。它的解释器被称为JavaScript引擎，为浏览器的一部分，广泛用于客户端的脚本语言，最早是在HTML网页上使用，用来给HTML网页增加动态功能。JavaScript兼容于ECMA标准，因此也称为ECMAScript。
> 基本特点
> 1．是一种解释性脚本语言（代码不进行预编译）。
> 2．主要用来向HTML（标准通用标记语言下的一个应用）页面添加交互行为。
> 3．可以直接嵌入HTML页面，但写成单独的js文件有利于结构和行为的分离。
> 4．跨平台特性，在绝大多数浏览器的支持下，可以在多种平台下运行（如Windows、Linux、Mac、Android、iOS等）。

17.	JavaScript的数据类型都有什么？
> 基本数据类型：String,boolean,Number,Undefined, Null
> 引用数据类型：Object(Array,Date,RegExp,Function)

18.	已知ID的Input输入框，希望获取这个输入框的输入值，怎么做？(不使用第三方框架)
> document.getElementById(“ID”).value;

19.	希望获取到页面中所有的checkbox怎么做？(不使用第三方框架)
document.querySelector("input[type=checkbox]");

20.	var numberArray = [3,6,2,4,1,5]; 
1) 实现对该数组的倒排，输出[5,1,4,2,6,3]
numberArray.reverse()
2) 实现对该数组的降序排列，输出[6,5,4,3,2,1]
numberArray.sort(function(a,b){return b-a})

21.	输出今天的日期，以YYYY-MM-DD的方式，比如今天是2014年9月26日，则输出2014-09-26

22.	为了保证页面输出安全，我们经常需要对一些特殊的字符进行转义，请写一个函数escapeHtml，将<, >, &, “进行转义
>	function escapeHtml(str) {
>		return str.replace(/[<>”&]/g, function(match) {
>    		switch (match) {
>                   case “<”:
>                      return “&lt;”;
>                   case “>”:
>                      return “&gt;”;
>                   case “&”:
>                      return “&amp;”;
>                   case “\””:
>                      return “&quot;”;
>      		}
>  		});
>	}

23.	foo = foo||bar ，这行代码是什么意思？为什么要这样写？
> if(!foo) foo = bar; //如果foo存在，值不变，否则把bar的值赋给foo。
> 短路表达式：作为”&&”和”||”操作符的操作数表达式，这些表达式在进行求值时，只要最终的结果已经可以确定是真或假，求值过程便告终止，这称之为短路求值。

24.	看下列代码，将会输出什么?(变量声明提升)
>	var foo = 1;
> (function(){
>     console.log(foo);
>     var foo = 2;
>     console.log(foo);
> })()
> 输出undefined 和 2。上面代码相当于：
> 	var foo = 1;
> (function(){
>     var foo;
>     console.log(foo); //undefined
>     foo = 2;
>     console.log(foo); // 2;   
> })()
> 函数声明与变量声明会被JavaScript引擎隐式地提升到当前作用域的顶部，但是只提升名称不会提升赋值部分。

25.	用js实现随机选取10–100之间的10个数字，存入一个数组，并排序。

26.	把两个数组合并，并删除第二个元素。
> var array1 = ['a','b','c'];
> var bArray = ['d','e','f'];
> var cArray = array1.concat(bArray);
> cArray.splice(1,1);

27.	怎样添加、移除、移动、复制、创建和查找节点（原生JS，实在基础，没细写每一步）
> 1. 创建新节点
>  createDocumentFragment()    //创建一个DOM片段
>  createElement()   //创建一个具体的元素
>  createTextNode()   //创建一个文本节点
> 2. 添加、移除、替换、插入
>  appendChild()      //添加
>  removeChild()      //移除
>  replaceChild()      //替换
>  insertBefore()      //插入
> 3. 查找
>  getElementsByTagName()    //通过标签名称
>  getElementsByName()     //通过元素的Name属性的值
>  getElementById()        //通过元素Id，唯一性

28.	有这样一个URL：http://item.taobao.com/item.htm?a=1&b=2&c=&d=xxx&e，请写一段JS程序提取URL中的各个GET参数(参数名和参数个数不确定)，将其按key-value形式返回到一个json结构中，如{a:’1′, b:’2′, c:”, d:’xxx’, e:undefined}。
> 答案：
> 	function serilizeUrl(url) {
>     var urlObject = {};
>     if (/\?/.test(url)) {
>         var urlString = url.substring(url.indexOf("?") + 1);
>         var urlArray = urlString.split("&");
>         for (var i = 0, len = urlArray.length; i < len; i++) {
>             var urlItem = urlArray[i];
>             var item = urlItem.split("=");
>             urlObject[item[0]] = item[1];
>         }
>         return urlObject;
>     }
>     return null;
> }
29.	正则表达式构造函数var reg=new RegExp(“xxx”)与正则表达字面量var reg=//有什么不同？匹配邮箱的正则表达式？
> 答案：当使用RegExp()构造函数的时候，不仅需要转义引号（即\”表示”），并且还需要双反斜杠（即\\表示一个\）。使用正则表达字面量的效率更高。 
> 邮箱的正则匹配：
> 	var regMail = /^([a-zA-Z0-9_-])+@([a-zA-Z0-9_-])+((.[a-zA-Z0-9_-]{2,3}){1,2})$/;

30.	看下面代码，给出输出结果。
> 	for(var i=1;i<=3;i++){
>   setTimeout(function(){
>       console.log(i);    
>   },0);  
> };
> 答案：4 4 4。
> 原因：Javascript事件处理器在线程空闲之前不会运行。追问，如何让上述代码输出1 2 3？
> 	for(var i=1;i<=3;i++){
>    setTimeout((function(a){  //改成立即执行函数
>        console.log(a);    
>    })(i),0);  
> };
 
31.	写一个function，清除字符串前后的空格。（兼容所有浏览器）
使用自带接口trim()，考虑兼容性：
> 	if (!String.prototype.trim) { 
>  String.prototype.trim = function() { 
>  return this.replace(/^\s+/, "").replace(/\s+$/,"");
>  } 
> } 
> 
> var str = " \t\n test string ".trim(); 
> alert(str == "test string"); // alerts "true"

32.	Javascript中callee和caller的作用？
> caller是返回一个对函数的引用，该函数调用了当前函数；
> callee是返回正在被执行的function函数，也就是所指定的function对象的正文。
那么问题来了？如果一对兔子每月生一对兔子；一对新生兔，从第二个月起就开始生兔子；假定每对兔子都是一雌一雄，试问一对兔子，第n个月能繁殖成多少对兔子？（使用callee完成）

33.	Javascript中, 以下哪条语句一定会产生运行错误？      答案(  B C  )
> var _变量=NaN;   B、var 0bj = [];   C、var obj = //;  	D、var obj = {};

34.	以下两个变量a和b，a+b的哪个结果是NaN？      答案(   AC  )
> A、var a=undefined; b=NaN 
> B、var a= ‘123’; b=NaN
> C、var a =undefined , b =NaN
> D、var a=NaN , b='undefined'

35.	var a=10; b=20; c=4;  ++b+c+a++ 以下哪个结果是正确的？答案(  B  )
> A、	34   B、35  C、36  D、37





