##一、 + 和 ~ 选择器的应用


        div+div{} 选择目标元素，下一个元素（后面的div）会被选中  2到5都被选中
        div~div{} 选择目标元素之后的所有元素     2到5都被选中
        .div~div{}  3到5都被选中
        .div+div{}  只选中3
   
        <div>1</div>
		<div class="div">2</div>
		<div>3</div>
		<div>4</div>
		<div>5</div>	

   
##二、 自定义字体 @font-face{}
		
		    /*自定义字体 声明自定义字体的名字 引入字体文件 指定字体文件的格式*/
		    @font-face{
		    font-family: "自定义名称";
		    src:
		    url(位置) format("字体文件的格式"),
		    url(位置) format("字体文件的格式");
		    }


##三、textarea的问题

            textarea标签能够拉动放大缩小，设置reszie：none可以去掉
		  
