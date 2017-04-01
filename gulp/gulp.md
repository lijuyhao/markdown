##gulp的使用
- 安装：npm install gulp-cli -g
- 查看版本：gulp -v
- 开始使用：
 1. npm init
 2. npm install gulp --save-dev
 3. 创建gulpfile.js
 4. gulp的插件gulp-uglify下载：npm install gulp-uglify --save-dev
 5. gulp的插件gulp-concat下载：npm install gulp-concat --save-dev
 6. gulp的插件gulp-cssnano下载:npm install gulp-cssnano --save-dev
 7. gulp的插件gulp-htmlmin下载：npm install gulp-htmlmin --save-dev
 8. 在gulpfiles.js里编写
   					
			 var gulp= require('gulp');   //得到gulp对象  
             var uglify = require('gulp-uglify')//引入gulp-uglify插件
             var concat = require('gulp-concat')//引入gulp-concat插件
             var cssnano =require('gulp-cssnano')//引入
             var htmlmin =require('gulp-htmlmin')//引入
             var browserSync =require('browser-sync');
		       
		     gulp.task('script',function(){  
		     gulp.src('[./app.js'，'./signIn.js]')  //匹配到文件   注意如果用到合并命令就需要两个位置  
             .pipe(concat（'all.js'）)       //合并命令
             .pipe(uglify())         //执行压缩，混淆的命令
		     .pipe(gulp.dest('./dist')) //输出到指定的目录
		      });    
                
             gulp.task('style',function(){  
                    gulp.src(['./style.css,./signIn.css'])
                    .pipe(concat('all.css'))
                    .pipe(cssnano())
                    .pipe(gulp.dest('./dest'))
                });

             gulp.task('html',function(){  
                   gulp.src('./index.html')   
                   .pipe(htmlmin({collapseWhitespace:true}))
                   .pipe(gulp.dest('./dist'))
                  });

             gulp.task('watch',function(){  
                 browserSync.init({
                 server:'./dist',
                 filse:['./dist/index.html']
                  });   
                 gulp.watch(['./app.css,./signIN.js'],['script'])//监听文件或者任务，自动跟新执行压缩

               })
		     
		      
    9.gulp script //执行任务命令
    

		  