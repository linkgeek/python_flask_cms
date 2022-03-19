## Flask CMS V2

初始的目录结构如下：

~~~
├── api api应用目录
│   ├── controllers api C层放在这里
│   └── interceptors 拦截器相关
├── application.py 封装的Flask的全局变量，包括app，数据库等
├── common 公用部分
│   ├── components 公用组件部分
│   ├── models 所有的数据库Model
│   └── services 公用服务
├── config 配置文件
│   ├── base_setting.py 通用配置文件
│   ├── local_setting_demo.py 本地环境配置文件demo，正常应该是 local_setting.py
├── docs 文档存放
│   └── mysql 数据库
├── jobs 定时任务目录
│   ├── BaseJob.py 定时器基类
│   ├── launcher.py  定时器框架启动类
│   └── tasks 应用定时器存放目录
├── manage_api.py api启动入口文件
├── manage_job.py 定时器启动入口文件
├── manage_web.py web启动入口文件
├── release.sh uwsgi控制脚本
├── requirements.txt 扩展依赖列表
├── route 路由入口目录
│   ├── api.py api路由入口目录
│   └── www.py web路由入口目录
├── uwsgi.ini uwsgi配置文件
└── web web应用目录
    ├── controllers web C层放在这里
    ├── interceptors 拦截器相关
    ├── static 静态文件：js、css
    └── templates 模板文件
~~~

官方文档：http://dcenter.jixuejima.cn/
GitHub：https://github.com/apanly/python_learn_master

### 安装依赖

扩展包官网：https://pypi.org/

1. flask包版本兼容
pip install flask==1.1.2

2. mysqlclient安装失败
https://www.lfd.uci.edu/~gohlke/pythonlibs/#mysqlclient，下载对应版本的whl文件安装

### 启动服务

1. 快速运行WEB
   python manage_web.py runserver

2. 访问地址

   http://127.0.0.1:8889  前台

   http://127.0.0.1:8889/home 后台
   
3. 执行测试Job：python manage_job.py runjob -m test