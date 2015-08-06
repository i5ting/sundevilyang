# sundevilyang

## 科普

### 什么是nodejs？

https://nodejs.org/

Node.js® is a platform built on Chrome's JavaScript runtime for easily building fast, scalable network applications. Node.js uses an event-driven, non-blocking I/O model that makes it lightweight and efficient, perfect for data-intensive real-time applications that run across distributed devices.

### 什么是npm？

npm = node package manager

see https://www.npmjs.com/

## 安装

nodejs版本也非常多，主要分为nodejs分支和iojs分支，所以建议使用nvm安装，以便更新和切换，测试不同版本的需要。

### nvm

To install nvm you could use the install script using cURL:

    curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.25.4/install.sh | bash
    
or Wget:

    wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.25.4/install.sh | bash


安装某个版本的nodejs

    nvm install v0.10.32

安装完成，需要切换版本，使用use

    nvm use 0.10

如果想系统默认采用该版本，可以执行

    nvm alias default 0.10.32


## hello world

### v1

helloworld.v1.js 代码

    var str = 'hello world';

    console.log(str)
    
测试结果

    ➜  sundevilyang git:(master) ✗ node helloworld.v1.js 
    hello world
    
### v2

helloworld.v2.js 代码

    function say(word){
      console.log(word)
    }

    var my_word = 'hello world';

    say(my_word);

测试结果

    ➜  sundevilyang git:(master) ✗ node helloworld.v2.js 
    hello world

## express入门

### 安装express-generator

express-generator是命令行生成express标准结构的生成器，比较简单易用

    npm install express-generator -g

### 创建express项目

    ➜  sundevilyang git:(master) ✗ express express-demo

       create : express-demo
       create : express-demo/package.json
       create : express-demo/app.js
       create : express-demo/public
       create : express-demo/routes
       create : express-demo/routes/index.js
       create : express-demo/routes/users.js
       create : express-demo/views
       create : express-demo/views/index.jade
       create : express-demo/views/layout.jade
       create : express-demo/views/error.jade
       create : express-demo/public/images
       create : express-demo/public/javascripts
       create : express-demo/public/stylesheets
       create : express-demo/public/stylesheets/style.css
       create : express-demo/bin
       create : express-demo/bin/www

       install dependencies:
         $ cd express-demo && npm install

       run the app:
         $ DEBUG=express-demo:* npm start

### 安装模块

npm是从源仓库下载模块到本地的node_modules目录的，所以不同的源可能速度不一样，建议采用nrm测试，切换到最快的源仓库。

    ➜  sundevilyang git:(master) ✗ cd express-demo 
    ➜  express-demo git:(master) ✗ npm install 
    debug@2.2.0 node_modules/debug
    └── ms@0.7.1

    cookie-parser@1.3.5 node_modules/cookie-parser
    ├── cookie@0.1.3
    └── cookie-signature@1.0.6

    serve-favicon@2.2.1 node_modules/serve-favicon
    ├── fresh@0.2.4
    ├── ms@0.7.1
    ├── parseurl@1.3.0
    └── etag@1.6.0 (crc@3.2.1)

    morgan@1.5.3 node_modules/morgan
    ├── basic-auth@1.0.3
    ├── depd@1.0.1
    └── on-finished@2.2.1 (ee-first@1.1.0)

    body-parser@1.12.4 node_modules/body-parser
    ├── bytes@1.0.0
    ├── content-type@1.0.1
    ├── depd@1.0.1
    ├── raw-body@2.0.2 (bytes@2.1.0)
    ├── qs@2.4.2
    ├── iconv-lite@0.4.8
    ├── on-finished@2.2.1 (ee-first@1.1.0)
    └── type-is@1.6.4 (media-typer@0.3.0, mime-types@2.1.2)

    express@4.12.4 node_modules/express
    ├── merge-descriptors@1.0.0
    ├── cookie-signature@1.0.6
    ├── utils-merge@1.0.0
    ├── methods@1.1.1
    ├── fresh@0.2.4
    ├── cookie@0.1.2
    ├── escape-html@1.0.1
    ├── range-parser@1.0.2
    ├── vary@1.0.1
    ├── content-type@1.0.1
    ├── finalhandler@0.3.6
    ├── parseurl@1.3.0
    ├── serve-static@1.9.3
    ├── content-disposition@0.5.0
    ├── path-to-regexp@0.1.3
    ├── depd@1.0.1
    ├── qs@2.4.2
    ├── etag@1.6.0 (crc@3.2.1)
    ├── on-finished@2.2.1 (ee-first@1.1.0)
    ├── proxy-addr@1.0.8 (forwarded@0.1.0, ipaddr.js@1.0.1)
    ├── accepts@1.2.10 (negotiator@0.5.3, mime-types@2.1.2)
    ├── type-is@1.6.4 (media-typer@0.3.0, mime-types@2.1.2)
    └── send@0.12.3 (destroy@1.0.3, ms@0.7.1, mime@1.3.4)

    jade@1.9.2 node_modules/jade
    ├── character-parser@1.2.1
    ├── void-elements@2.0.1
    ├── commander@2.6.0
    ├── with@4.0.3 (acorn-globals@1.0.4, acorn@1.2.2)
    ├── constantinople@3.0.1 (acorn-globals@1.0.4)
    ├── mkdirp@0.5.1 (minimist@0.0.8)
    └── transformers@2.1.0 (promise@2.0.0, css@1.0.8, uglify-js@2.2.5)
    

### 启动服务器

    ➜  express-demo git:(master) ✗ npm start

    > express-demo@0.0.0 start /Users/sang/workspace/github/sundevilyang/express-demo
    > node ./bin/www

### 访问

在浏览器中打开

    http://127.0.0.1:3000/

## express练习

### 了解目录结构
    
    ➜  express-demo git:(master) ✗ tree . -L 2
    .
    ├── app.js
    ├── bin
    │   └── www
    ├── node_modules
    │   ├── body-parser
    │   ├── cookie-parser
    │   ├── debug
    │   ├── express
    │   ├── jade
    │   ├── morgan
    │   └── serve-favicon
    ├── package.json
    ├── public
    │   ├── images
    │   ├── javascripts
    │   └── stylesheets
    ├── routes
    │   ├── index.js
    │   └── users.js
    └── views
        ├── error.jade
        ├── index.jade
        └── layout.jade

    15 directories, 8 files

说明

- bin/www是入口，配置服务器端口，最终调用核心app.js启动服务器
- app.js是主要文件，配置中间件等
- app.js里会挂载routes里面定义的所有路由
- 了解routes里的路由写法和http verb含义
- 了解res.render用法
- 了解views目录和jade语法
- 了解static http server
- 最后了解一下package.json的一些npm技巧

### web

- html (jade)
- js (jQuery)
- css (Stylus with bootstrap)

bootcss.com

### 了解http协议，以get和post为例子，熟悉路由写法

http://expressjs.com/starter/basic-routing.html

### 了解jade基本语法以及布局

jade-lang.com

- 基本语法（把之前联系的html使用jade重写一遍）
- 熟悉控制结构（if、for等指令）
- include（头文件和partial）
- extend（布局）

## db

以mongodb为主

### mongodb安装

    brew install mongodb(for mac)

### mongodb简单客户端crud命令

Robomongo 0.8.4（for mac）


Visit Robomongo website: www.robomongo.org 

### 学习mongoose用法crud

创建表结构

- 用户
  - 用户名
  - 密码

完成用户表的crud


创建Post表

- Post
  - title
  - body
  - user_id

完成Post的crud，注意此时使用的callback完成的。

学习populate用法

    Post.find({"_id" : mongoose.Types.ObjectId("55c2ca1979624c1a98ce9d04")}).populate('create_by').exec(function(err,data){
      ...
    });

改造callback为promise方式

    User.createAsync({name:'kezhi',password:'333',age:20}).then(function(u){  
      return Post.createAsync({title:'夏天到了',content:'树叶绿了',create_by: u._id})
    }).then(function(){
      ...
    }).catch(function(err){
      console.log(err);
    });


文档见mongoosejs.com/docs/ or mongoosedao

- crud
- statics和methods
- pre和post回调
- plugin插件
- Aggregate

### 学习mocha测试mongoose用法

https://github.com/nodeonly/mongoose-test

## 实例：完成一个简单的博客

- 实现用户登录、注册
- 实现创建topic功能
- 实现回复功能
- 实现jade layout布局
- 如果精力，介绍promise/a+规范，并改写controller里的逻辑

## deploy

- git.oschina
- 灵雀云 Alauda or heroku or ngork 


## FAQ

### nvm 和 npm 的关系是什么？  类似于Ruby中的 rvm 和 bundler 吗？

对的，非常准确

Rails 3 中引入Bundle来管理项目中所有gem依赖，该命令只能在一个含有Gemfile的目录下执行，如rails 3项目的根目录

npm实际是对package.json管理node module的。

