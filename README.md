# title: 使用Hexo搭建个人博客之旅

我相信每个just do it的人都会想拥有自己的博客。
早年间玩过jekyll，很湿麻烦，没搭建成功过，囧！！后来发现了[Hexo](http://theme-next.iissnan.com/)这玩意，可以说是一键部署，还不需要服务器数据库之类，只要懂点nodejs，会点MarkDown语法，买个域名就行了.so easy！    


## Step1 环境配置    

#### 1、安装node
[安装教程](http://www.runoob.com/nodejs/nodejs-install-setup.html)
Mac上安装，执行下面命令：
```
nmp install -g node
```

#### 2、安装git
[安装教程](https://git-scm.com/book/zh/v2/%E8%B5%B7%E6%AD%A5-%E5%AE%89%E8%A3%85-Git)
Mac上自带

#### 3、申请github
提供[github](https://github.com/)地址，自行注册就行。

#### 4、安装hexo
```
sudo npm install -g hexo
```

#### 5、初始化项目
先创建你的项目目录，然后cd到该目录下，执行初始化操作：
```
hexo init
```

#### 6、生成静态页面
在你项目目录下执行命令：
```
hexo generate (或 hexo g)
```

#### 7、本地服务启动
调试看看
```
hexo server (或 hexo s)
```
然后浏览器访问http://localhost:4000/ 就可以看到效果啦。

#### 8、建立Repository
前提：建立与你用户名对应的仓库，仓库名必须为【your_user_name.github.io】.
现在我们需要修改_config.yml(该文件就在项目跟目录下)文件，来建立关联，执行命令：
```
vim _config.yml
```
在最下面，改为：（注意： : 后面要有空格;wyh2020改为你的github帐号名）
```
deploy:
  type: git
  repository: https://github.com/wyh2020/wyh2020.github.io.git
  branch: master
```

#### 9、部署
先执行下面命令才能进行部署：
```
npm install hexo-deployer-git --save
```
部署命令：
```
hexo deploy (或hexo d)
```
然后在浏览器中浏览 http://wyh2020.github.io 就OVER了(wyh2020改为你的github帐号名).
#### 10、配置域名
我申请的是万网(已经被阿里收购了)，一定要实名认证哦. 不然没效果.
域名解析配置如图：
![域名解析配置](/uploads/域名解析截图.jpg)

#### 11、其它
每次部署的步骤，可按以下三步来进行.
```
hexo clean
hexo generate
hexo deploy
```
常用命令：
```
hexo new "postName" #新建文章
hexo new page "pageName" #新建页面
hexo generate #生成静态页面至public目录
hexo server #开启预览访问端口（默认端口4000，'ctrl + c'关闭server）
hexo deploy #将.deploy目录部署到GitHub
hexo help  # 查看帮助
hexo version  #查看Hexo的版本
```




