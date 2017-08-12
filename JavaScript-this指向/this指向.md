# JavaScript this指向  

### 前言  
	在js中，this是必须要掌握的知识点，　首先必须要说的是，this的指向在函数定义的时候是确定不了的，只有函数执行的时候才能确定this到底指向谁，实际上this的最终指向的是那个调用它的对象。我将在以下文章中举例说明this指向问题；
	
首先我们都知道对于一个定义在全局上的变量和函数来言，我们可以视为他是定义在window对象下的属性或方法。
	
	举个例子来说
	var a = 1；
	function a(){
    	console.log(this); //Window
    	console.log(this.a)；//1
	}
	a();
	这个其实就可以看作是
	window.a()
	这里的this指向window
	所以打印出来的结果是window、1
	  
	
	当我们定义一个对象来说  
	var meng = {
	 	name:"孟",
    	fn:function(){
        	console.log(this.name);  //追梦子
    	}
	}
	如果我们调用meng对象下的fn函数
	meng.fn();
	打印出来的结果就是 “孟“	
	这里说明的是this的最终指向的是那个调用它的对象，我孟这里调用他的不是window，而是meng
	所以	，这里this的指向是meng


	而在构造函数中this的指向是是用new关键字定义了的实列化对象
	function Fn(){
    	this.name = "meng";
	}
	var a = new Fn();
	console.log(a.name); //meng
	这里的this指向的是


	在事件绑定中this指向事件出发的元素
	例如
	btn.onclick = function（）{
		var btn.index = 1;
		console.log(this.index)// 1		
	
	}
	这里的this指向btn
	
	
	在jq中 this的指向始终是事件出发的元素
	列如
	$("div").click(function(){
		$(this).css({background,"red"})
	})	
	这个函数会在div点击时改变div的背景颜色。
	
	
## 希望我的文章对大家有所帮助。




	

