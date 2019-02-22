# django-vue.js-book
django rest framework + vue 的图书管理小项目，前后端分离教程


## 环境

- Python 2.7
    - Django 1.11.6
    - Django Rest Framework 3.8
    
- Vue.js 2.9
    - iview 2.8
    - iview-admin 1.3
    
## 依赖

```
#升级pip
wget --no-check-certificate https://bootstrap.pypa.io/get-pip.py
python get-pip.py
pip install --upgrade pip -i https://pypi.douban.com/simple/
pip install -r backend/requirements.txt -i https://pypi.douban.com/simple/

###安装虚拟环境
pip install virtualenv

###激活虚拟环境
virtualenv /usr/local/demo2 --no-site-packages
source  /usr/local/demo2/bin/activate

#mysql模块
pip install -i https://pypi.mirrors.ustc.edu.cn/simple/ pymysql
###在工程目录中的__init__.py中添加如下代码
vim restful_test/__init__.py

import pymysql
pymysql.install_as_MySQLdb()
```
## 数据库操作
```
# 创建数据库
mysql -h 127.0.0.1 -u root -p123456 -e "create database rest default character set utf8mb4 collate utf8mb4_unicode_ci;"

# 执行数据库同步操作
python manage.py makemigrations
python manage.py migrate

1、创建超级管理员
python manage.py createsuperuser
python manage.py createsuperuser --username admin --email admin@domain.com

2、修改密码
python manage.py changepassword admin

3、清除sessions
python manage.py clearsessions

#快速生成requirements.txt文件
pip freeze > requirements.txt

#安装requirements依赖
pip install -i https://pypi.mirrors.ustc.edu.cn/simple/  -r requirements.txt
```

## 前端部署
```bash
# install dependencies
npm install --unsafe-perm     // 出现权限问题，可添加此参数重试
npm install --registry=https://registry.npm.taobao.org

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report

```

## 功能

- 简单的图书数据管理，结合豆瓣API做图书信息查询

## 界面

- 图书列表
![image](https://github.com/myide/django-vue.js-book/blob/master/images/list.png)

- 图书详情
![image](https://github.com/myide/django-vue.js-book/blob/master/images/detail.png)

## 交流学习
- QQ群 630791951

## 报错
```
报错一：
WrappedAttributeError: 'CSRFCheck' object has no attribute 'process_request'

解决办法：
pip install --upgrade django==1.11.6 -i https://pypi.douban.com/simple/
```

## 修改前端监听端口

https://stackoverflow.com/questions/33272967/how-to-make-the-webpack-dev-server-run-on-port-80-and-on-0-0-0-0-to-make-it-publ
