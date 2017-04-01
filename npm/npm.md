##npm 的使用方法 
- node package manager
- cd [路径]  进入当前位置
- npm init  初始化
- npm install jquery --save
- 如果有了json文件可以使用：npm install --production  来下载对应版本的东西
- 要使用指定版本的：npm install jquery@3.0.0 --save
- 移除包：npm remove jquery --save
## browser-sync ##
- 安装browser-sync:npm install broswer-sync -g
- 检查版本号:browser-sync --version
- 开始使用：browser-sync start --server --files'./index.html'