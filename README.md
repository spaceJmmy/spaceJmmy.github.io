# 部署三部曲

&emsp;&emsp;&ensp;以后写博客可以用hexo new post-title，也可以自己写md，然后放到/source/_posts文件夹下，写好博客后，来个拉风的部署三部曲，呼呼：
  ``` bash
  $ hexo clean #清空缓存
  $ hexo d #部署站点到master分支
  $ hexo b #备份站点源代码到src分支
  ```

# 换台电脑重新部署
&emsp;&emsp;&ensp;得益于前面的工作，换台电脑我们只需要clone仓库的src分支，然后重新生成hexo博客环境来撰写和发布post。
``` bash
$ git clone -b src git@github.com:spaceJmmy/spaceJmmy.github.io.git
$ cd spaceJmmy.github.io
$ cnpm install
```
hexo环境搭建成功，然后撰写md，执行 hexo s 本地预览，再按上述的部署三部曲走起，呼呼...
有时 hexo b 会报错，提示执行 git push，那就 git push，你会看到 push 成功，哈哈。
