##一、@media 媒体查询

    
    <!DOCTYPE html>
    <html>
    	
    <head>
		<meta charset="UTF-8">
		<title></title>
	</head>
	<style type="text/css">
		body,
		html {
			margin: 0;
			padding: 0;
		}
		
		.container {
			width: 1200px;
			margin: 0 auto;
			background: red;
			height: 1000px;
		}
		
		@media screen and (max-width:768px) {
			.container {
				width: 100%;
				background: green;
			}
		}
		
		@media screen and (min-width: 768px) and (max-width: 992px) {
			.container {
				width: 100%;
				background: yellow;
			}
		}
		
		@media screen and (min-width:992px) and (max-width:1200px) {
			.container {
				width: 100%;
				background: blue;
			}
		}
		
		@media screen and (min-width:1200px) {
			.container {
				width: 100%;
				background: pink;
			}
		}
	</style>

	<body>
		<div class="container">

		</div>
	</body>

</html>

>超小屏幕(移动设备)　　　　768px  
小屏幕设备　　　　　　　768px-992px  
中等屏幕　　　　　　　　992px-1200px  
 



##二、bootstrap官方基础模板  代码解释
	```
	<!DOCTYPE html>  声明了一个标准的html5文档类型  
	<html lang="zh-CN">--声明这个文档是一个中文简体语言的文本，在一些非这类语言类型的机器语言上，浏览器可识别，比如说在美国打开这个网页，就可以翻译
	<head>
	  <meta charset="utf-8">  -- 声明页面的字符编码是 utf-8  国际通用编码格式，高大上
	  <meta http-equiv="X-UA-Compatible" content="IE=edge">  声明ie浏览器需要用最新的渲染引擎来渲染当前的页面，因为有时ie不会使用最新渲染引擎
	  <meta name="viewport" content="width=device-width, initial-scale=1 user-scalable=0">只有移动端才识别， 视口的宽等于设备宽，初始缩放比1比1，显示在移动端，不允许用户自行缩放
	  <!-- 上述3个meta标签*必须*放在最前面，任何其他内容都*必须*跟随其后！ -->
	  <title>Bootstrap 101 Template</title>
	
	  <!-- Bootstrap -->
	  <link href="css/bootstrap.min.css" rel="stylesheet">
	  
	  在不支持 html5标签的浏览器和不支持media查询的浏览器我们使用下面两个js插件来做兼容
	  有条件注释 在ie9以下的版本浏览器 使用下面两个js文件 
	
	  <!-- HTML5 shim and Respond.js for IE8 support of HTML5 elements and media queries -->
	  <!-- WARNING: Respond.js doesn't work if you view the page via file:// --> 注意要在http形式下才能正常使用下面两个文件，因为有ajax请求
	  <!--[if lt IE 9]>
	  <script src="//cdn.bootcss.com/html5shiv/3.7.2/html5shiv.min.js"></script>
	  <script src="//cdn.bootcss.com/respond.js/1.4.2/respond.min.js"></script>
	  <![endif]-->
	</head>
	  <body>
	<h1>你好，世界！</h1>
	
	<!-- jQuery (necessary for Bootstrap's JavaScript plugins) -->
	<script src="//cdn.bootcss.com/jquery/1.11.3/jquery.min.js"></script>
	<!-- Include all compiled plugins (below), or include individual files as needed -->
	<script src="js/bootstrap.min.js"></script>
	  </body>
	</html>
	```





##三、布局容器 　　.container　　.container-fliud


** 　　Bootstrap 需要为页面内容和栅格系统包裹一个 .container 容器，我们提供了两个作此用处的类。  
注意，由于 padding 等属性的原因，这两种 容器类不能互相嵌套。**

	>- .container 类用于固定宽度并支持响应式布局的容器。
	```
	<div class="container">
	  ...
	</div>
	```
	
	>- .container-fluid 类用于 100% 宽度，占据全部视口（viewport）的容器。
	```
	<div class="container-fluid">
	  ...
	</div>
	```


##四、bootstrap栅格系统

　　Bootstrap提供了一套响应式，移动设备优先的流式栅格系统，随着屏幕或视口(viewport)尺寸的增加，系统会自动分为最多12列。
它包含了易于使用的预定义类。  
    
    
-     “行（row）”必须包含在 .container （固定宽度）或 .container-fluid （100% 宽度）中， 以便为其赋予合适的排列（aligment）和内补（padding）。        

-     通过“行（row）”在水平方向创建一组“列（column）”。        

-     你的内容应当放置于“列（column）”内，并且，只有“列（column）”可以作为行（row）”的直接子元素。    

-     类似 .row 和 .col-xs-4 这种预定义的类，可以用来快速创建栅格布局。Bootstrap 源码中定义的 mixin 也可以用来创建语义化的布局。  

-     通过为“列（column）”设置 padding 属性，从而创建列与列之间的间隔（gutter）。通过为 .row 元素设置负值 margin 从而抵消掉为 .container 元素设置的 padding，也就间接为“行（row）”所包含的“列（column）”抵消掉了padding。  

-     负值的 margin就是下面的示例为什么是向外突出的原因。在栅格列中的内容排成一行。  

-     栅格系统中的列是通过指定1到12的值来表示其跨越的范围。例如，三个等宽的列可以使用三个 .col-xs-4 来创建。  

-     如果一“行（row）”中包含了的“列（column）”大于 12，多余的“列（column）”所在的元素将被作为一个整体另起一行排列。  

-     栅格类适用于与屏幕宽度大于或等于分界点大小的设备 ， 并且针对小屏幕设备覆盖栅格类。 因此，在元素上应用任何 .col-md-\* 栅格类适用于与屏幕宽度大于或等于分界点大小的设备 ， 并且针对小屏幕设备覆盖栅格类。 因此，在元素上应用任何 .col-lg-\* 不存在， 也影响大屏幕设备。


##五、 bootstrap里的css的问题

1、  为什么.container要加上padding-left:15px,而.row要加上margin-left:-15px去抵消，从而container和row的边界是在一起的。如果想到这样的效果，两个元素都不加上padding和margin不是直接就可以了？  
  
2、.container的内的直接子元素都是.row吧？这样才符合Bootstrap提出的栅格化布局

     第一个问题应该是十二栏布局的时候就已经决定好了的。这个十五个像素的gap(间隙)应该可以在less 见里面去调整的.
     在我看来更多的是提供的一种思路啊不是你一定要用它。
     第二个问题 container 直接直接子元素数也可以不是row。当多个元素要去水平排列的时候才会用row
     而且row在我看来应该是更多的是为了自适应布局存在的。


##六、  bootstrap 偏移盒子
>-   使用col-md-offset-3 来进行偏移


##七、Carousel  旋转木马  官方的轮播图代码解释
		```
		<div id="carousel-example-generic" class="carousel slide" data-ride="carousel">
		  <!-- Indicators -->    //指示器
		  
		  下面的是小圆点，控制id为carousel-example-generic的容器的，data-slide-to来对应上是哪一张图片。
		  <ol class="carousel-indicators">
		    <li data-target="#carousel-example-generic" data-slide-to="0" class="active"></li>
		    <li data-target="#carousel-example-generic" data-slide-to="1"></li>
		    <li data-target="#carousel-example-generic" data-slide-to="2"></li>
		  </ol>
		
		  <!-- Wrapper for slides -->    //轮播内容的大容器
		  <div class="carousel-inner" role="listbox">
		    <div class="item active">
		      <img src="..." alt="...">
		      <div class="carousel-caption">
		         <h3>...</h3>            //这个是设置轮播图的说明的
		         <p>...</p>
		      </div>
		    </div>
		    <div class="item">
		      <img src="..." alt="...">
		      <div class="carousel-caption">
		        ...
		      </div>
		    </div>
		    ...
		  </div>
		
		
		 控制左右两个箭头的
		  <!-- Controls -->
		  <a class="left carousel-control" href="#carousel-example-generic" role="button" data-slide="prev">
		    <span class="glyphicon glyphicon-chevron-left" aria-hidden="true"></span>
		    <span class="sr-only">Previous</span>
		  </a>
		  <a class="right carousel-control" href="#carousel-example-generic" role="button" data-slide="next">
		    <span class="glyphicon glyphicon-chevron-right" aria-hidden="true"></span>
		    <span class="sr-only">Next</span>
		  </a>
		</div>
		```


##八、在使用bootstrap carousel（旋转木马）js插件时的css问题，background-size:contain  和cover的区别     

>- 在设定好盒子的高度后，contain会显示图片的整体，而cover只会显示部分填充高度超出盒子.

##九、bootstrap carousel 使用背景图片的问题

>- 在响应式开发中background-image设置的背景图片是不能自适应的，所以在做移动端的页面的时候要使用img标签配合比较小的图片来做。

##十、bootstrap carousel banner图在适配移动端和pc端的屏幕大小产生的问题

>- 使用两张不同尺寸相同内容的图片来适配大小，因为写了两个图片盒子所以使用hidden-sm来适配，但是，问题来了
     在使用的时候两张图片都会同时加载，加重了请求量，所以要想个方法在移动端屏幕的时候只请求移动端的banner图片
   在pc端的屏幕大小的时候只请求pc端的banner图片，解决思路如下
  
   ```
    /*
	 *1、获取后台的轮播图路径  图片数据   （ajax）
	 *2、需要判断当前的屏幕是移动端还是非移动端    （ 屏幕的宽度768px以下都是移动端）
	 *3、把后台数据渲染成对应的html字符串      (字符串拼接，可以通过js或者模板引擎)
	 *4、把渲染完成的html填充在对应的盒子里面  也就是完成了页面的渲染   (通过.html()形式渲染到页面)
	 *5、在屏幕尺寸改变的时候需要重新渲染页面     (监听页面尺寸的改变 resize)
	 */
	
	    首先自己要写个json数据把图片的地址写在里面:
	[
	  {
	    "img":"images/slide_01_640x340.jpg",
	    "bg":"images/slide_01_2000x410.jpg"
	  },
	  {
	    "img":"images/slide_02_640x340.jpg",
	    "bg":"images/slide_02_2000x410.jpg"
	  },
	  {
	    "img":"images/slide_03_640x340.jpg",
	    "bg":"images/slide_03_2000x410.jpg"
	  },
	  {
	    "img":"images/slide_04_640x340.jpg",
	    "bg":"images/slide_04_2000x410.jpg"
	  }
	]
   ```  

