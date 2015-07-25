title: 通过Hexo与github搭建一个静态的个人博客
date: 2015-07-25 19:52:38
categories: 建站
tags: [Hexo, github, 博客] #文章标签，可空，多标签请用格式，注意:后面有个空格
description: 通过Hexo与github搭建一个静态博客 | Sun's Blog
---

这篇博客记录了我搭建我的个人博客的全过程。网络上有很多关于搭建个人博客的文章，但很多文章都不全，这里完整的记录了我搭建这儿静态博客的过程，希望可以帮助有相同需求的人。

##前言
为什么要写博客，因为我想就下自己在学习和生活中的点点滴滴。以前学习很多东西，看一两遍就记住了。但是最近发现自己的记性没有以前好了，所以就想到了建个博客。一来可以把自己学习经验和生活感触写下来，二来是可以和大家分享自己的那么一点点有用的东西。

为什么要开博客？可以看看cnFeat的这篇[《为什么你要写博客？》](http://zhuanlan.zhihu.com/cnfeat/19743861)

或者也可看看这篇文章[《我的博客时代》](http://zhuanlan.zhihu.com/cnfeat/19743255)

有人会问为什么要搭建一个属于自己的独立博客，网上有很多博客网站可以选择。答案很简单，一个独立的博客是真正属于自己的。

##为什么选择hexo和Github Pages
很多人用wordpress，你为什么要用github pages来搭建？
1. github pages有300M免费空间，资料自己管理，保存可靠；
2. 学着用github，享受github的便利，上面有很多大牛，眼界会开阔很多；
3. 顺便看看github工作原理，最好的团队协作流程；
4. github是趋势；
5. 你不觉得一个文科生用github很geek吗？瞬间跻身技术界；
6. 就算github被墙了，我可以搬到国内的gitcafe中去。

hexo可以帮助生成静态页面。



##GitHub Pages是什么？
GitHub Pages本用于介绍托管在GitHub上的项目， 不过，由于他的空间免费稳定，用来做搭建一个博客再好不过了。

>github Pages可以被认为是用户编写的、托管在github上的静态网页。
![](http://cnfeat.qiniudn.com/1.png)

##购买域名
只推荐上godaddy购买，安全，而且可以使用支付宝。

教程（截止至2014年5月10日）如下

**1、查你想要的域名；**
![](http://cnfeat.qiniudn.com/2.png)

**2、查到适合的域名之后选择「continue to Cart」;**
![](http://cnfeat.qiniudn.com/3.png)

**3、godaddy附加收费服务，不要管，继续「continue to Cart」;**
![](http://cnfeat.qiniudn.com/4.png)

**4、确认购买。**修改购买年限，默认是两年，可以修改成1/2/3/5/10年，随自己喜欢。现在godaddy上com每年的默认费用是12.99美元，附加上ICANN的管理费用就是13.17美元。
![](http://cnfeat.qiniudn.com/5.png)
如果你不是土豪，可以上网搜godaddy的优惠码，一大堆，找一个填进这里，填完之后，一年的费用会变成8.99美元。
![](http://cnfeat.qiniudn.com/61.png)

**说明一下：**一般来讲，使用网上的优惠码第一年收费8.99美元，以后每年的收费是10.99美元，不过在网上可以搜到合适的优惠码，可以每年的收费都是8.99美元，记得多测试自行鉴别。

如图，我买了五年的费用就是45.85美元，随后点击「Proceed to Checkout」

![](http://cnfeat.qiniudn.com/6.png)

**5、结算。**登录或注册界面，填完必要的信息之后，选择用支付宝结算。
![](http://cnfeat.qiniudn.com/7.png)
如果以上的教程如果不够清晰，可以参照这一份[《2013年10月新版godaddy域名注册图文教程》](http://www.admin5.com/article/20131014/527495.shtml)。

**6、检查。**结算后，重新登录，去「My Account」，域名已经显示在你的账户了。
![](http://cnfeat.qiniudn.com/8.png)

**7、补充一些注意事项：**

--输入优惠码没有优惠或者优惠幅度较低，请清除浏览器cookies再尝试；
--如果没有支付宝支付选项，有可能是使用的优惠码不支持支付宝，请重新清除浏览器cookies再尝试；
--注册时用户填写信息时一定要输入正确的邮箱名字，否则修改十分麻烦。
--买完域名之后一定要记得去自己的邮箱查看激活邮件，否则域名激活不了。

## 安装所需软件
安装下来软件：
--{Node.js](http://nodejs.org/)
--[Git](http://git-scm.com/)

## 打开Git
可以通过下面两种方式打开Git：
--Windows开始菜单的快捷方式it Bash
！[](http://cnfeat.qiniudn.com/9.jpg)
--鼠标右键打开Git Bash
![](http://cnfeat.qiniudn.com/s10.jpg)

## 验证Node.js是否安装成功
在Windows下win+R打开运行，输入cmd回车
![]()
打开命令行窗口
![]()
在命令行窗口输入node回车，出现下面的提示表示安装成功
![]()

## 注册Github
访问：[www.github.com](http://www.github.com)

注册你的username和邮箱，邮箱十分重要，GitHub上很多通知都是通过邮箱的。

注册过程比较简单，详细也可以看：
[一步步在GitHub上创建博客主页全系列](http://pchou.info/web-build/2013/01/03/build-github-blog-page-01.html)

## 配置SSH keys
要想让本地的给项目与在github上的项目联系，需要使用SSH keys。

### 检查SSH keys的设置

首先我们需要检查你电脑上现有的ssh key：

```bash
$ cd ~/.ssh   检查本机的ssh密钥
```
如果提示：No such file or directory 说明你是第一次使用git。


### 生成新的SSH Key：
```bash
$ ssh-keygen -t rsa -C "邮件地址@youremail.com"
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/your_user_directory/.ssh/id_rsa):<回车就好>
```

注意1: 此处的邮箱地址，你可以输入自己的邮箱地址；注意2: 此处的「-C」的是大写的「C」

然后系统会要你输入密码：

```bash
Enter passphrase (empty for no passphrase):<输入加密串>
Enter same passphrase again:<再次输入加密串>
```
在回车中会提示你输入一个密码，这个密码会在你提交项目时使用，如果为空的话提交项目时则不用输入。这个设置是防止别人往你的项目里提交内容。

注意：输入密码的时候没有*字样的，你直接输入就可以了。

最后看到这样的界面，就成功设置ssh key了：
![](http://cnfeat.qiniudn.com/11.png)

### 添加SSH Key到GitHub

在本机设置SSH Key之后，需要添加到GitHub上，以完成SSH链接的设置。

--打开本地C:\Documents and Settings\Administrator.ssh\id_rsa.pub文件。此文件里面内容为刚才生成人密钥。如果看不到这个文件，你需要设置显示隐藏文件。准确的复制这个文件的内容，才能保证设置的成功。

--登陆github系统。点击右上角的 Account Settings—->SSH Public keys —-> add another public keys

--把你本地生成的密钥复制到里面（key文本框中）， 点击 add key 就ok了
![](http://cnfeat.qiniudn.com/s12.jpg)

### 测试
可以输入下面的命令，看看设置是否成功，git@github.com的部分不要修改：
```bash
$ ssh -T git@github.com
```
如果是下面的反馈：
```bash
The authenticity of host 'github.com (207.97.227.239)' can't be established.
RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.
Are you sure you want to continue connecting (yes/no)?
```
不要紧张，输入yes就好，然后会看到：
```bash
Hi cnfeat! You've successfully authenticated, but GitHub does not provide shell access.
```
### 设置用户信息

现在你已经可以通过SSH链接到GitHub了，还有一些个人信息需要完善的。

Git会根据用户的名字和邮箱来记录提交。GitHub也是用这些信息来做权限的处理，输入下面的代码进行个人信息的设置，把名称和邮箱替换成你自己的，名字必须是你的真名，而不是GitHub的昵称。
```bash
$ git config --global user.name "cnfeat"//用户名
$ git config --global user.email  "cnfeat@gmail.com"//填写自己的邮箱
```
### SSH Key配置成功
本机已成功连接到github。

若有问题，请重新设置。常见错误请参考：

[GitHub Help - Generating SSH Keys](http://help.github.com/articles/generating-ssh-keys)

[GitHub Help - Error Permission denied (publickey)](http://help.github.com/articles/error-permission-denied-publickey)

## 使用GitHub Pages建立博客
与GitHub建立好链接之后，就可以方便的使用它提供的Pages服务，GitHub Pages分两种，一种是你的GitHub用户名建立的username.github.io这样的用户&组织页（站），另一种是依附项目的pages。

想建立个人博客是用的第一种，形如[suen427.github.io](https://suen427.github.io)这样的可访问的站，每个用户名下面只能建立一个。


### github上建立仓库

登录后系统，在github首页，点击页面右下角「New Repository」
![](http://cnfeat.qiniudn.com/13.png)
填写项目信息：

**project name：**cnfeat.github.io

**description：** Sun's Blog

注：Github Pages的Repository名字是特定的，比如我Github账号是suen427，那么我Github Pages Repository名字就是suen427.github.io。
点击「Create Repository」完成创建。

详细可以看这里：[一步步在GitHub上创建博客主页(2)](http://pchou.info/web-build/2013/01/05/build-github-blog-page-02.html)

## 用Hexo克隆主题
### Hexo介绍
Hexo的作者是[tommy351](https://github.com/tommy351/hexo)，根据[官方介绍](http://hexo.io/docs/index.html)，Hexo是一个简单、快速、强大的博客发布工具，支持Markdown格式。

### 安装Hexo
利用 npm 命令即可安装。(在任意位置点击鼠标右键，选择Git bash)
```bash
$ npm install -g hexo
```
### 部署Hexo

安装完成后，在你喜爱的文件夹下（如`H:\hexo`），执行以下指令(在`H:\hexo`内点击鼠标右键，选择Git bash)，Hexo 即会自动在目标文件夹建立网站所需要的所有文件。
```bash
$ hexo init
```
### 安装依赖包
```bash
$ npm install
```
### 本地查看
现在我们已经搭建起本地的hexo博客了，执行以下命令(在`H:\hexo`)，然后到浏览器输入`localhost:4000`看看。
```bash
$ hexo generate
$ hexo server
```
### 复制博客的主题
建立了Hexo文件之后复制wuchong的修改的主题，我的就是复制他的修改的。
```bash
$ git clone https://github.com/wuchong/jacman.git themes/jacman
```
或者复制yangjian的
```bash
$ git clone https://github.com/A-limon/pacman.git themes/pacman
```
### 启用博客的主题
修改`Hexo`目录下的`_config.yml`配置文件中的`theme`属性，将其设置为`jacman`。
```bash
theme: jacman
```
注意：Hexo有两个`_config.yml`文件，一个在根目录，一个在`theme`下，此时修改的是在根目录下的。
### 更新主题
```bash
$ cd themes/jacman
$ git pull
```
注意：为避免出错，请先备份你的`_config.yml`文件后再升级。

### 使用与调试
在本地如果需要预览或者调试你的博客，可以启动本地服务器：
```bash
hexo serve
```
部署到Github前需要配置`_config.yml`文件。
```bash
deploy:
type: github
repository: git@github.com:suen427/suen427.github.io.git
branch: master
```
如果你是为一个项目制作网站，那么需要把branch设置为gh-pages。若要绑定自定义域名也可以参考Hexo或Github Page的帮助文档，制作一个cname文件。

之后执行下列指令即可完成部署，注意部署会覆盖掉你之前在版本库中存放的文件。
```bash
$ hexo clean
$ hexo generate
$ hexo deploy
```

## 将独立域名与GitHub Pages的空间绑定
### GitHub Pages的设置

方法一：在Repository的根目录下面，新建一个名为CNAME的文本文件，里面写入你要绑定的域名，比如suen427.com。

方法二：到我的github仓库，点击右下角的「Download ZIP」，下载源文件，解压，找到CNAME文件，用记事本打开，将suen427.com修改成你的域名，放进Hexo\source目录下，用hexo命令提交上去。

### DNS设置

用DNSpod，快，免费，稳定。

注册DNSpod，添加域名，如下图设置。
![](http://cnfeat.qiniudn.com/15.png)

其中A的两条记录指向的ip地址是github Pages的提供的ip

-192.30.252.153
-192.30.252.154

如博客不能登录，有可能是github更改了空间服务的ip地址，记得及时到在[GitHub Pages](https://help.github.com/articles/setting-up-a-custom-domain-with-github-pages)查看最新的ip即可

www指定的记录是你在github注册的仓库。

### 去Godaddy修改DNS地址
更改godaddy的Nameservers为DNSpod的NameServers。
![](http://cnfeat.qiniudn.com/16.png)
1、点击「My Account」，管理我的域名。
![](http://cnfeat.qiniudn.com/17.jpg)
2、点击域名。
![](http://cnfeat.qiniudn.com/18.jpg)
3、将godaddy的Nameservers更改成f1g1ns1.dnspod.net和f1g1ns2.dnspod.net
![](http://cnfeat.qiniudn.com/19.jpg)
如有不详看可以看[DNSpod提供的官方帮助](https://support.dnspod.cn/Kb/showarticle/tsid/42/)

详细也可以看这里：[一步步在GitHub上创建博客主页(3)](http://pchou.info/web-build/2013/01/05/build-github-blog-page-03.html)

## 搭建完成
至此，独立博客就算搭建完成，如需进步一完善请在参看以下文章或博客下留言。

[Pacman主题介绍](http://yangjian.me/workspace/introducing-pacman-theme/) by yangjian

[使用hexo搭建博客](http://yangjian.me/workspace/building-blog-with-hexo/) by yangjian

[hexo系列教程：（二）搭建hexo博客](http://zipperary.com/2013/05/28/hexo-guide-2/) by zippera（推荐）

[hexo系列教程：（三）hexo博客的配置、使用](http://zipperary.com/2013/05/29/hexo-guide-3/) by zippera（推荐）

## 进阶篇：Hexo设置

网站搭建完成后，就可以根据自己爱好来对Hexo生成的网站进行设置了，对整站的设置，只要修改项目目录的`_config.yml`就可以了，这是我的设置，可供参考。

```bash
# Hexo Configuration
## Docs: http://hexo.io/docs/configuration.html
## Source: https://github.com/hexojs/hexo/

# Site #整站的基本信息
title: Sun's Blog #网站标题
subtitle: 记录学习成长的点点滴滴  #网站副标题
description: 个人博客 学习分享 笔记 随笔 #网站描述
author: Sun #网站作者
email: suen427@gmail.com #联系邮箱
language: zh-CN #网站语言
timezone: Asia/Shanghai #时区

# URL
## If your site is put in a subdirectory, set url as 'http://yoursite.com/child' and root as '/child/'
url: http://suen427.github.io #你的域名
root: /
permalink: :year/:month/:day/:title/
permalink_defaults:

# Directory
source_dir: source
public_dir: public
tag_dir: tags
archive_dir: archives
category_dir: categories
code_dir: downloads/code
i18n_dir: :lang
skip_render:

# Writing
new_post_name: :title.md # File name of new posts
default_layout: post
titlecase: false # Transform title into titlecase
external_link: true # Open external links in new tab
filename_case: 0
render_drafts: false
post_asset_folder: false
relative_link: false
future: true
highlight:
  enable: true
  line_number: true
  auto_detect: true
  tab_replace:

# Category & Tag
default_category: uncategorized
category_map:
tag_map:

# Archives
## 2: Enable pagination
## 1: Disable pagination
## 0: Fully Disable
archive: 2
category: 2
tag: 2

# Date / Time format
## Hexo uses Moment.js to parse and display date
## You can customize the date format as defined in
## http://momentjs.com/docs/#/displaying/format/
date_format: YYYY-MM-DD
time_format: HH:mm:ss

# Pagination
## Set per_page to 0 to disable pagination
per_page: 10
pagination_dir: page

# Extensions
## Plugins: https://github.com/tommy351/hexo/wiki/Plugins
## Themes: https://github.com/tommy351/hexo/wiki/Themes
theme: jacman
plugins:
- hexo-generator-feed
- hexo-generator-sitemap

#Feed Atom
feed:
  type: atom
  path: atom.xml
  limit: 20

# Markdown
## https://github.com/chjj/marked
markdown:
  gfm: true
  pedantic: false
  sanitize: false
  tables: true
  breaks: true
  smartLists: true
  smartypants: true

# Stylus
stylus:
  compress: false

# Deployment
## Docs: http://hexo.io/docs/deployment.html
deploy:
  type: git
  repository: git@github.com:suen427/suen427.github.io.git
```

### 修改局部页面

页面展现的全部逻辑都在每个主题中控制，源代码在hexo\themes\jacman\中：
```bash
.
├── languages  #多语言
|   ├── default.yml#默认语言
|   └── zh-CN.yml  #中文语言
├── layout #布局，根目录下的*.ejs文件是对主页，分页，存档等的控制
|   ├── _partial   #局部的布局，此目录下的*.ejs是对头尾等局部的控制
|   └── _widget#小挂件的布局，页面下方小挂件的控制
├── source #源码
|   ├── css#css源码 
|   |   ├── _base  #*.styl基础css
|   |   ├── _partial   #*.styl局部css
|   |   ├── fonts  #字体
|   |   ├── images #图片
|   |   └── style.styl #*.styl引入需要的css源码
|   ├── fancybox   #fancybox效果源码
|   └── js #javascript源代码
├── _config.yml#主题配置文件
└── README.md  #用GitHub的都知道
```
### Hexo命令

常用命令：
```bash
hexo new "postName" #新建文章
hexo new page "pageName" #新建页面
hexo generate #生成静态页面至public目录
hexo server #开启预览访问端口（默认端口4000，'ctrl + c'关闭server）
hexo deploy #将.deploy目录部署到GitHub
```
简写：
```bash
hexo n == hexo new
hexo g == hexo generate
hexo s == hexo server
hexo d == hexo deploy
```
常用复合命令：
```bash
hexo d -g #生成加部署
hexo s -g #预览加部署
```

### 发表新文章

用hexo发表新文章
```bash
$ hexo n #写文章 
```
其中my new post为文章标题，执行命令后，会在项目\source_posts中生成my new post.md文件，用编辑器打开编写即可。

当然，也可以直接在\source_posts中新建一个md文件。

写完后，推送到服务器上，执行
```bash
$ hexo g #生成
$ hexo d #部署 # 可与hexo g合并为 hexo d -g
```
### 用Hexo发表文章的Markdown语法

使用jacman或pacman主题，建议按此标准语法写：
```bash
title: postName #文章页面上的显示名称，可以任意修改，不会出现在URL中
date: 2013-12-02 15:30:16 #文章生成时间，一般不改，当然也可以任意修改
categories: example #分类
tags: [tag1,tag2,tag3] #文章标签，可空，多标签请用格式，注意:后面有个空格
description: 附加一段文章摘要，字数最好在140字以内。
---

以下正文
```

## 安装插件
添加sitemap和feed插件
```bash
$ npm install hexo-generator-sitemap
$ npm install hexo-generator-feed
```
修改`_config.yml`，增加以下内容
```bash
# Extensions
Plugins:
- hexo-generator-feed
- hexo-generator-sitemap

#Feed Atom
feed:
  type: atom
  path: atom.xml
  limit: 20

#sitemap
sitemap:
  path: sitemap.xml
```
## Hexo上传README文件

Github的版本库通常建议同时附上README.md说明文件，但是hexo默认情况下会把所有md文件解析成html文件，所以即使你在线生成了README.md，它也会在你下一次部署时被删去。怎么解决呢？

在执行hexo deploy前把在本地写好的README.md文件复制到`public`文件夹中，再去执行`hexo deploy`。

## 404页面

GitHub Pages有提供制作404页面的指引：[Custom 404 Pages](https://help.github.com/articles/custom-404-pages)。

直接在根目录下创建自己的404.html或者404.md就可以。但是自定义404页面仅对绑定顶级域名的项目才起作用，GitHub默认分配的二级域名是不起作用的，使用hexo server在本机调试也是不起作用的。

## 图床

推荐使用七牛（10G空间，免费）。

## RSS插件

hexo提供了RSS的生成插件，需要手动安装和设置。使用插件 `hexo-generator-feed` 能生成 `Atom 1.0` 或者 `RSS 2.0 feed`. 安装很简单
```bash
$ npm install hexo-generator-feed --save
```
然后在 `Hexo` 根目录下的 `_config.yml` 里配置一下
```bash
feed:
    type: atom
    path: atom.xml
    limit: 20
```
-type 表示类型, 是 atom 还是 rss2.
-path 表示 Feed 路径
-limit 最多多少篇最近文章

## sitemap
同样的，我们使用插件 hexo-generator-sitemap 能生成站点地图, 方法如下
```bash
$ npm install hexo-generator-sitemap --save
```
然后在 `Hexo` 根目录下的 `_config.yml` 里配置一下
```bash
sitemap:
    path: sitemap.xml
```
-path 表示 Sitemap 的路径. 默认为 sitemap.xml.
对于国内用户还需要安装插件 hexo-generator-baidu-sitemap, 顾名思义是为百度量身打造的. 安装
```bash
$ npm install hexo-generator-baidu-sitemap --save
```
然后在 Hexo 根目录下的 _config.yml 里配置一下
```bash
baidusitemap:
    path: baidusitemap.xml
```

## 参考资料：
[1][如何搭建一个独立博客——简明Github Pages与Hexo教程](http://cnfeat.com/2014/05/10/2014-05-11-how-to-build-a-blog/)
[2][Hexo 优化与定制(二)](http://lukang.me/2015/optimization-of-hexo-2.html)
[3][hexo系列教程：（二）搭建hexo博客](http://zipperary.com/2013/05/28/hexo-guide-2/)

## 感谢
[cnFeat](http://cnfeat.com/)

[wuchong](http://wuchong.me/)

[yangjian](http://yangjian.me/)

