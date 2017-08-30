---
title: Hexo博客撰写之：MarkDown语法介绍
date: 2017-08-27 09:12:00
categories:
  - 其他
tags:
  - hexo
  - markdown
description: 本文介绍如何在hexo搭建的博客下用markdown写文章,以及一些markdown的基本语法．
photos:
  - https://gss3.bdstatic.com/-Po3dSag_xI4khGkpoWK1HF6hhy/baike/c0%3Dbaike150%2C5%2C5%2C150%2C50/sign=62597ff6ba51f819e5280b18bbdd2188/908fa0ec08fa513d7ddc9503376d55fbb3fbd9fd.jpg
  
---


# 新歌推送
　　消除联萌是JJ林俊杰精心筹划了近一年的全新“虚拟乐团”，这次是JJ首次以“师父”的身份亲自带领四名正式团员亮相。JJ还特别邀请获得包括“年度制作”及“最佳摇滚专辑”等多项格莱美殊荣的“混音之王”Chris Lord-Alge参与制作，强烈风格让这首歌有着让人一听着迷的魅力。据悉，《丹宁执着》的灵感就是来自那个“改变时尚世界的牛仔裤”的爱情故事。而JJ被这样的爱情所打动，有感而发的写下了这首歌。

<center>
**《丹宁执着》电台预听完整版 － 林俊杰/消除联萌**
<video width="320" height="220" src='http://tb-video.bdstatic.com/tieba-smallvideo/250_9e5fdc5aaa8282d45cfcbccd677d3f35.mp4' controls='controls' > 
您的浏览器不支持 video 标签。 
</video>
</center>

【歌曲详情】
　　你可知道，你身上穿的那件牛仔裤，蕴含著爱情，还浇注了一分热忱和感动。
　　当布商 Levi Strauss 和裁缝师 Jacob Davis 得知一位女性客户提出，请他们缝製出一条耐用不怕磨损的裤子，给心爱的丈夫在砍伐木材时穿著不那麽容易破损，使他们製作加固牛仔裤的概念得到启发，进而改变世界的牛仔裤诞生了!
　　JJ林俊杰深深被这样纯粹的爱情打动，加上「丹宁」精神就是既结实又柔软，已有许多隽永的爱情篇章写不完，那就用这份对音乐的热忱与纯粹，以阳光般温暖的音符谱出这首听来热血沸腾的「消除联萌」首支单曲《丹宁执著》!
　　这次也因著JJ林俊杰一如既往对作品的坚持信念，希望将最棒的作品呈现给大家，特别请到了「神级混音大师」Chris Lord-Alge 为这首《丹宁执著》进行混音。Chris Lord-Alge 是美国知名混音师，如果你喜欢摇滚乐，那你一定十分熟悉他的声音!
　　Chris Lord-Alge 参与过的专辑获得许多葛莱美奖，他也拥有另外一个名字叫「Lord of the Mix(混音之王)」，因为他的风格强烈，会让人听过就难以忘怀的著迷。

---

# 前言
　　搭建好了ｈｅｘｏ，接下来的就是写博客了， hexo 支持用 markdown 写博客，markdown 语法很简单，本文给出一些基本的 markdown 语法，结合 hexo 教你如何在 hexo 下用 markdown 撰写ｐｏｓｔ．

# hexo 博客头部
　　hexo 博客的 markdown 头部有固定的格式，如下所示：
``` markdown
---
title: Hexo博客撰写之：MarkDown语法介绍
date: 2017-08-27 09:12:00
categories:
  - 其他
tags:
  - hexo
  - markdown
description: 本文介绍如何在hexo搭建的博客下用markdown写文章,以及一些markdown的基本语法．
photos:
  - https://gss3.bdstatic.com/-Po3dSag_xI4khGkpoWK1HF6hhy/baike/c0%3Dbaike150%2C5%2C5%2C150%2C50/sign=62597ff6ba51f819e5280b18bbdd2188/908fa0ec08fa513d7ddc9503376d55fbb3fbd9fd.jpg
  
---
```
顾名思义，我们很容易看懂这个头部信息．
我们写新博客的时候只需要复制这些内容，然后对相应的内容进行修改，但不要修改格式．


# hexo 博客正文
　　hexo 博客正文就是正常的 markdown 了，下面就介绍一些基本的 markdown 语法．

# 基本的 markdown 语法
- ## 标题
通过在行首插入 1 到 6 个 # ，来定义 1 到 6 阶 标题，对应 html 的 `<h1>`到`<h6>` 标签：

| **Markdown** | **预览** |
| :---: | :---: |
| `# 一级标题` | <font size=5>**一级标题**</font> |
| `## 二级标题` | <font size=4>**二级标题**</font> |
| `### 三级标题` | <font size=3>**三级标题**</font> |
| `#### 四级标题` | <font size=2>**四级标题**</font> |
| `##### 五级标题` | <font size=1>**五级标题**</font> |
| `###### 六级标题` | <font size=0>**六级标题**</font> |


- ## 段落和换行
  在 Markdown 中段落由一行或者多行文本组成，相邻的两行文字会被视为同一段落，如果存在空行则被视为不同段落( Markdown 对空行的定义是看起来是空行就是空行，即使空行中存在 空格 TAB 回车 等不可见字符，同样会被视为空行)。

  Markdown支持段内换行，如果你想进行段落内换行可以在上一行结尾插入两个以上的空格后再回车。

| **Markdown** | **预览** |
| --- | --- |
| 第一行<br>相邻被视为同一段落。 | <p>第一行 相邻被视为同一段落。 </p> |
| 第一行[空格][空格]<br>上一行结尾存在两个空格，段内换行  | <p>第一行<br>上一行结尾存在两个空格，段内换行。</p> |
| 第一行<br><br>两行之间存在空行，视为不同段落。 | <p>第一行</p><p>两行之间存在空行，视为不同段落。</p> |


- ## 缩进
  输入法中文全角状态下输入两个空格即可实现缩进．输入两个　&emsp;　或　&ensp;　也可以实现空格缩进．


- ## 强调

| **Markdown** | **预览** |
| :---: | :--- |
| *倾斜* | <i>倾斜</i> |
| **粗体** | <b>粗体</b> |
| ~~删除线~~ | <s>删除线</s> |
| >引用 | <blockquote>引用</blockquote> |


- ## 链接和图片

| **Markdown** | **预览** |
| :---: | :---: |
| `[百度一下](https://www.baidu.com/)` | [百度一下](https://www.baidu.com/) |
| `![《丹宁执着》封面图片](https://gss3.bdstatic.com/-Po3dSag_xI4khGkpoWK1HF6hhy/baike/c0%3Dbaike150%2C5%2C5%2C150%2C50/sign=62597ff6ba51f819e5280b18bbdd2188/908fa0ec08fa513d7ddc9503376d55fbb3fbd9fd.jpg)` | ![《丹宁执着》封面图片](https://gss3.bdstatic.com/-Po3dSag_xI4khGkpoWK1HF6hhy/baike/c0%3Dbaike150%2C5%2C5%2C150%2C50/sign=62597ff6ba51f819e5280b18bbdd2188/908fa0ec08fa513d7ddc9503376d55fbb3fbd9fd.jpg) |


- ## 音频和视频
  可以直接使用html的 `<audio>` 和　`<video>` 标签嵌入　音频　和　视频．比如以下视频标签：

 **Markdown:** 
  ```
  <center>
  <video width=320 height=200 src='http://tb-video.bdstatic.com/tieba-smallvideo/32_054ab95c5e7edd7a22c913fd1d1d8a5c.mp4' controls='controls' > 
  您的浏览器不支持 video 标签。 
  </video>
  </center>
  ```

  **预览:**   
  <center>
  <video width=320 height=200 src='http://tb-video.bdstatic.com/tieba-smallvideo/32_054ab95c5e7edd7a22c913fd1d1d8a5c.mp4' controls='controls' > 
  您的浏览器不支持 video 标签。 
  </video>
  </center>




- ## 列表
  无序列表用 - 引领列表内容，
  有序列表用　数字　引领列表内容，
  需要指出的是：有序列表的数字即便不按照顺序排列，结果仍是有序的。

| **Markdown** | **预览** |
| :--- | :--- |
| - 项目<br>- 项目<br>　- 子项目<br>　- 子项目<br>- 项目 | <small>●</small> 项目<br><small>●</small> 项目<br>　　<small>●</small> 子项目<br>　　<small>●</small> 子项目<br><small>●</small> 项目 |
| 1. 项目<br>2. 项目<br>　1. 子项目<br>　2. 子项目<br>3. 项目 | 1. 项目<br>2. 项目<br>　　1. 子项目<br>　　2. 子项目<br>3. 项目 |
| 1. 项目<br>３. 项目<br>　6. 子项目<br>　4. 子项目<br>２. 项目 | 1. 项目<br>2. 项目<br>　　1. 子项目<br>　　2. 子项目<br>3. 项目 |


- ## 下划线和特殊符号
  由于 Markdown 使用一些特殊符号进行标记，当我们想要在文档中使用这些特殊符号并防止被 Markdown 转换的时候，可以使用 `\` (转义符) 将这些特殊符号进行转义。

| **Markdown** | **预览** |
| :---: | :---: |
| 在一行中用三个以上的减号来建立一个分隔线<br>\-\-\- | <hr> |
| 可以利用反斜杠(转义字符)来插入一些在语法中有特殊意义的符号<br>`\*Hi\*`  | \*Hi\* |


- ## 代码
  **1.行内代码**
  行内代码可以使用反引号来标记(反引号一般位于键盘左上角，要用英文．

| **Markdown** | **预览** |
| :---: | :---: |
| 一句话 \`行内代码\` 一句话 | 一句话`行内代码`一句话 |
| 就比如\` < video > \`标签  | 就比如 `<video>` 标签  |


  **2.多行代码**
  多行代码使用 3 个反引号来标记(反引号一般位于键盘左上角，要用英文) ，在第一个 \`\`\` 后面可以跟语言类型，没有语言类型可以省略不写:

 **Markdown:** 
  ```
    ``` javascript
    // 我是注释
    var a = 5 ;
    console.log(a)
    ``` 
  ```

  **预览:**   
  ``` javascript
  // 我是注释
  var a = 5 ;
  console.log(a)
  ```



- ## 表格
  
**Markdown:** 
| 默认  |   靠右 |  居中  | 靠左   |
| \-\-\-\- |  \-\-\-: | :\-\-:  | :\-\-\-  |
| 内容  |   内容 |  内容  | 内容   |
| 内容  |   内容 |  条目  | 内容   |


**预览:**   
  
| 默认  |   靠右 |  居中  | 靠左   |
| ---- |  ---: | :--:  | :---  |
| 内容  |   内容 |  内容  | 内容   |
| 内容  |   内容 |  条目  | 内容   |




---
　　OK先到这里,基本语法就是这样，以后如果学到新的好用语法了，我会继续推送的^_^







