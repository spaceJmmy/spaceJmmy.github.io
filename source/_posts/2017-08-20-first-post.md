---
title: 第一篇post：庆祝博客搭建成功
date: 2017-08-20 
categories:
  - 其他
tags:
  - 教程
  - hexo
  - node
  - git
photos:
  - https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1503148516430&di=2c41bb485a605fff7536d8c4da59fbc2&imgtype=0&src=http%3A%2F%2Fsc.sinaimg.cn%2F2013%2F0409%2FU4885P841DT20130409081537.jpg
description: 记录博客搭建过程和感受
---


&emsp;&emsp;&ensp;先来听一听这段时间很有感触的一首歌... &emsp; 《追光者》
<center>

<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=330 height=86 src="//music.163.com/outchain/player?type=2&id=483671599&auto=0&height=66"></iframe>
备份音乐《追光者》
<audio src='http://mp3.haoduoge.com/s/2017-06-20/1497945728.mp3' controls='controls' > 
您的浏览器不支持 audio 标签。 
</audio> 
<br>
歌曲《追光者》，电视剧《夏至未至》插曲，立夏人物曲。由唐恬作词，马敬作曲，岑宁儿细腻地唱出剧中角色立夏面对爱情委婉又小心翼翼的模样，诠释了这首歌盛满纯真的感觉，收录于专辑《夏至未至 电视原声带》中，发行于2017年06月16日。
</center>

---

# 前言
&emsp;&emsp;&ensp;一直想搭建自己的博客，但是一直没实践，只怪自己太懒。这次终于下定决心去实践，不过像我等小白来来回回折腾了好几天，本来想省点事直接在github上小改一下，谁知道老是出问题，一提交就收到Page build failure邮件，头疼的我差点放弃，最后狠下心来在本地安装了jekyll，一边调试一边修改，总算调通了，然后push到github，刷新主页，-_-，404找不到页面！妈呀，搜了好久解决办法，最后按照网上说的bundle update升级到了和github一样的最新版，这次报错了：MethedError：not find methed to_liquid for...想了半天，当前'github-pages'包的最新版是155,我把Gemfile中的'github-pages'改成了'github-pages', '~> 154'，也就是从默认的当前最新版本155降到了154,运行bundel exec jekyll serve，完美通过。。。我就郁闷了，原来这个jekyll-next主题已经不适用最新版的github-pages了。那怎么办呢，直接用hexo+next吧，索性静态页面就静态到底吧。

# hexo+next搭建过程（基于ubuntu） 
- 注册github账户
- 新建一个<usrname.github.io>仓库，因为静态网站提交到这个仓库的master分支之后，访问 https://usrname.github.io 就可以看到网站啦^_^
- 安装node
- 安装git
- 安装Hexo
  这里先安装cnpm，以加快npm包的下载速度：
  ``` bash
  npm install -g cnpm --registry=https://registry.npm.taobao.org
  ```
  然后，安装hexo
  ``` bash
  $ cnpm install hexo -g
  ```
- 初始化框架
  ```bash
  $ hexo init <blog-folder>
  $ cd <blog-folder>
  $ cnpm install
  ```
-  安装Next主题
  ``` bash
  $ cd your-hexo-site
  $ git clone https://github.com/iissnan/hexo-theme-next themes/next
  ```
  修改站点_config.yml配置项theme：
  ```
  theme: next
  ```
- 配置启用local_search
  ``` bash
  $ cd your-hexo-site
  $ cnpm install hexo-generator-search --save
  ```
  编辑站点_config.yml，增加以下内容：
  ```
  search:
    path: search.xml
    field: post
    format: html
    limit: 10000
  ```
- 安装hexo-deployer-git
  ``` bash
  $ cd your-hexo-site
  $ cnpm install hexo-deployer-git --save
  ```
  修改站点_config.yml：
  ```
  deploy:
    type: git
    repo: <repository url>
    branch: [branch]
    message: 提交信息(默认为 Site updated: {{ now(YYYY-MM-DD HH:mm:ss) }})
  ```
- 新建文章
  ``` bash
  $ hexo new "Hello World"
  ```
  此时会在/source/_post目录下添加hello-world.md文件
- 添加关于页面
  ``` bash
  $ hexo new page about
  ```
  此时会在/source/目录下生成about文件夹
- 添加分类
  ``` bash
  $ hexo new page categories
  ```
  此时会在/source/目录下生成categries文件夹，
  编辑里面的index.md，添加 type: categories
- 添加标签
  ``` bash
  $ hexo new page tags
  ```
  此时会在/source/目录下生成tags文件夹，
  编辑里面的index.md，添加 type: tags
- 生成网站
  ``` bash
  $ hexo generate 
  或者 
  $ hexo g
  ```
  此时会将/source中的.md文件生成到/public中，形成网站的静态文件。
- 本地服务
  ``` bash
  $ hexo server
  或者
  $ hexo s
  ```
  便可预览网站
- 部署网站
  ``` bash
  $ hexo deploy
  或者
  $ hexo d

  ```
---

&emsp;&emsp;&ensp;等等， hexo d 之后出现了下面信息：
``` bash
$ INFO  Deploying: git
$ You have to configure the deployment settings in _config.yml first!

$ Example:
$   deploy:
$     type: git
$     repo: <repository url>
$     branch: [branch]
$     message: [message]

$     extend_dirs: [extend directory]

$ For more help, you can check the docs: http://hexo.io/docs/deployment.html

```
搜索了解决办法，但不是很明确，试了半天，最后原来是多了一个空格，就是_config.yml中
```
deploy:
空格空格type: git

```
改成
```
deploy:
空格type: git
```
就好了,真是好难发现啊！

---
# github设置添加SSH key
- 本地生成ssh key
https每次push需要输入用户名和密码，为了以后部署方便，我们使用ssh提交，使用ssh需要配置添加SSH key，具体如下：
``` bash
$ cd ~/.ssh
$ ssh-keygen -C "your_computer_name"
```
接着会提示输入文件名，默认就行了，Enter
再接着会提示你输入两次密码，这个是push时候的密码，我们选择空密码，Enter
没问题的话就成功了。
- 添加ssh key到github
``` bash
$ clip < ~/.ssh/id_rsa.pub
```
然后登录github，进入右上角Account Settings，然后点击菜单栏的SSH key进入页面添加key，
点击Add SSH key按钮，把复制的SSH key代码粘贴到key所对应的输入框，点击确认，Title会默认使用你的邮件名称。
- 测试该SSH key
``` bash
$ ssh -T git@github.com
```
出现
``` bash
$ Hi spaceJmmy! You've successfully authenticated, but GitHub does not provide shell access.
$ Connection to github.com closed.
```
OK，测试成功^_^

---

# 增加源码备份功能
&emsp;&emsp;&ensp;能够部署静态网站之后，我们还想把网站的源码备份到远程仓库，我们的思路是master分支存放生成的静态页面，src分支存放网站的源代码，这样以后换台机器可以直接clone下来src分支，然后添加发布新的post。这里推荐一个很好的npm包，可以实现源码备份功能，叫作[hexo-git-backup
](https://github.com/coneycode/hexo-git-backup)，下面进行安装配置：
``` bash
$ cnpm install hexo-git-backup --save
```
然后配置站点_config.yml文件，
``` bash
$ backup:
$     type: git
$     message: update xxx
$     repository:
$        github: git@github.com:spaceJmmy/spaceJmmy.github.io.git,src
$        #gitcafe: git@github.com:xxx/xxx.git,branchName
```
之后便可使用
``` bash
$ hexo backup
```
或者
``` bash
$ hexo b
```
进行源码备份。

# 部署三部曲

&emsp;&emsp;&ensp;以后写博客可以用hexo new post-title，也可以自己写md，然后放到/source/_posts文件夹下，写好博客后，来个拉风的部署三部曲，呼呼：
  ``` bash
  $ hexo clean #清空缓存
  $ hexo d #部署站点到master分支
  $ hexo b #备份站点源代码到src分支
  ```

---

# 换台电脑重新部署（记得添加新的SSH key）
&emsp;&emsp;&ensp;得益于前面的工作，换台电脑我们只需要clone仓库的src分支，然后重新生成hexo博客环境来撰写和发布post。
``` bash
$ git clone -b src git@github.com:spaceJmmy/spaceJmmy.github.io.git
$ cd spaceJmmy.github.io
$ cnpm install
```
hexo环境搭建成功，然后 hexo s 本地预览，添加新的post，再按上述部署三部曲走起，呼呼...
有时 hexo b 会报错，提示执行 git push，那就 git push，你会看到 push 成功，哈哈。

---

&emsp;&emsp;&ensp;至此大功告成，看着自己现在这个博客上线，心里确实美滋滋啊，haha。

---

&emsp;&emsp;&ensp;这个博客的搭建，要感谢很多人...
- 首先感谢github，提供了git pages来托管我们的博客，而且是免费的;
- 然后要感谢提供主题模板的开源贡献者，使得像我这样的小白能够用上这么高大上的博客;
- 最后要感谢我自己，能够下定决心克服搭建博客的困难，谁让我是小白呢，慢慢进步喽^_^







