##一、安装mysql
##二、配置环境变量，在环境path中添加c盘mysql 的bin目录
##三、启动mysql服务：net start mysql
##四、如果启动不成功初始化以下mysql：mysqld --initialize
##五、停止mysql服务：net stop mysql
##六、查看版本：mysql -V
##七、
    1.-D，--database=name    打开指定数据库
    2.--delimiter=name       指定分隔符
    3.-h,--host=name         服务器名称
    4.-p,--password[=name]   密码
    5.-P,--port=#            端口号
    6.--prompt=name          设置提示符
    7.-u,--user=name         用户名
    8.-V，--version          输出版本信息并且退出
##八、mysql -uroot -p -P3306 -h127.0.0.1  默认端口是3306
##九、退出mysql：exit;
##十、mysql提示符
    1.\D   完整的日期
    2.\d   当前数据库
    3.\h   服务器名称
    4.\u   当前用户
##十一、修改提示符：prompt \u@\h \d>   
##十二、显示当前服务版本：SELECT VERSION();
##十三、显示当前日期时间：SELECT NOW();
##十四、显示当前用户：    SELECT USER();
##十五、关于第一次运行超级用户密码的问题：
		   mysql，新版本mysql root不在是空密码，而是初始化时生成一个随机密码，在msql
		   安装目录data文件夹下 .err 格式文件里 
           A temporary password is generated for root@localhost: qd;DzH&5h5wn  
           qd;DzH&5h5wn 就是密码
##十六、如何修改密码：
           set password for root@localhost = password('123');
##十七、创建数据库：
           CREATE {DATABASE|SCHEMA}  [IF NOT EXISTS]  db_name  //存在还可以创建数据库 SHOW WARNINGS
           [DEFAULT] CHARACTER SET [=] charset_name            //SHOW CREATE DATABASE t1 查看编码 
           //已经有了数据库，修改编码
           ALTER  {DATABASE|SCHEMA} [db-name]
           [DEFAULT] CHARACTER SET [=] charset_name
           //删除数据库
           DROP {DATABASE|SCHEMA} [IF EXISTS] db_name