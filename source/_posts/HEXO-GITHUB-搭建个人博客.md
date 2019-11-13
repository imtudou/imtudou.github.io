---
title: HEXO + GITHUB 搭建个人博客
date: 2019-07-29 14:27:56
tags:
    - hexo
categories: 随笔
---

## 一：GitHub 配置 + SSH
#### 准备工作

```
    需要注册一个GitHub 账号
    有Node.JS Git 环境并了解相关知识
    了解Markdown语法相关知识
```
#### 创建GitHub仓库
新建一个`xxx.github.io`的仓库。比如说你的GitHub用户名为`zhagsan`
那么你就建一个仓库名为`zhangsan.github.io`以后直接访问这个地址即可。

`
注意：
仓库名必须以 xxx.github.io 命名 并且 xxx 必须为你的用户名 否则无法访问
`

#### 配置SSH
生成SSH 密钥
![n5Le0.png](HEXO-GITHUB-搭建个人博客/images/n5Le0.png)

添加SSH 密钥
![n5xJp.png](HEXO-GITHUB-搭建个人博客/images/n5xJp.png)

#### 绑定域名
当然，你不绑定域名肯定也是可以的，就用默认的 xxx.github.io 来访问，如果你想更个性一点，就直接在阿里云上买一个域名就可以了。

域名配置最常见有2种方式

CNAME和A记录，CNAME填写域名，A记录填写IP，由于不带www方式只能采用A记录，所以必须先ping一下你的用户名`.github.io`的IP，然后到你的域名DNS设置页，将A记录指向你ping出来的IP,将CNAME指向你的`xxx.github.io`，这样可以保证无论是否添加www都可以访问，如图

域名解析
![n5ZyE.png](HEXO-GITHUB-搭建个人博客/images/n5ZyE.png)




## 二：NexT主题个性化
#### 设置语言

编辑 站点配置文件， 将 language 设置成你所需要的语言。建议明确设置你所需要的语言，例如选用简体中文，配置如下：
```
language: zh-Hans
```
此处需要注意的是:我一开始语言设置为`language: zh-Hans`发现不行 然后去next的语言库发现只有zh-CN这个文件 把主站配置语言设置为 `language: zh-CN`就好了


#### 设置菜单
此处需要更改的目录为（也就是下载后的next主题所在的文件夹，此处我将next主题的文件夹名称改为了`NexT`） `/themes/NexT/_config.yml`

搜索 "menu" 段落后直接将注释的菜单注释回来 如下配置：
```
menu:
  home: / || home
  about: /about/ || user
  tags: /tags/ || tags
  categories: /categories/ || th
  archives: /archives/ || archive
  schedule: /schedule/ || calendar
  sitemap: /sitemap.xml || sitemap
  commonweal: /404/ || heartbeat
```

#### 创建对应的菜单
如：标签页 和 分类页

标签页：`hexo new page tags` 可简写为：`hexo n page tags`

分类页：`hexo new page categories`  可简写为：`hexo n page categories`

命令输入完成后 查看根目录下的`/source` 文件里会有两个名为 `tags`和`categories`的文件夹
分别点击进去编辑名为`index.md`会发现有如下类容：

```
title: tags
date: 2019-07-13 22:50:02
```

我们需要更改成如下内容：
```
title: 分类
date: 2019-07-13 22:50:02
type: "tags" 
```


#### 主题设置
在该路径下 `/themes/NexT/_config.yml`搜索`Scheme Settings`

会看到如下四种主题

```
# Schemes
# scheme: Muse
# scheme: Misty
#scheme: Pisces
scheme: Gemini

```

选中对应的注释回来即可

#### 新建文章
`hexo new xxx` 会看见在在根目录对应的`source/_posts/`文件里有一个对应的`.md`文件

如： `hexo new 第一篇博客 ` 会对应的看到 `第一篇博客.md`
编辑该文件

```
title: 第一篇博客
date: 2019-07-14 12:40:28
tags:
	 - 心情
	 - 杂谈
categories: 随笔
```



[NexT 官方文档](http://theme-next.iissnan.com/getting-started.html#avatar-setting)

[B站视频讲解](https://www.bilibili.com/video/av55890967/?p=1)

[B站视频讲解-系列](https://www.bilibili.com/video/av17653359)







## 三：Hexo博客多台电脑设备同步管理
我们通过 `hexo d`命令发布到`xxx.github.io`仓库里的是发布文件，那我每次写的博客文件的源码该如何存放呢？（网上说通过github分支的原理存放源码，刚好我也是真么做的）

- 创建分支（在`xxx.github.io`仓库下操作）

  1.创建分支
  ![n5aqe.png](HEXO-GITHUB-搭建个人博客/images/n5aqe.png)

  2.将分支设置成默认
  ![n5hwg.png](HEXO-GITHUB-搭建个人博客/images/n5hwg.png)
  
  

- 文件合并


 在任意路径下  执行`git clone https://github.com/imtudou/imtudou.github.io.git`将刚刚新建 的hexo分支克隆到本地。接下来在克隆到本地的`imtudou.github.io`中，把除了.git 文件夹外的所有文件都删掉。
 
 把之前我们写的博客源文件全部复制过来，除了`.deploy_git`这里应该说一句，复制过来的源文件应该有一个`.gitignore`，用来忽略一些不需要的文件，如果没有的话，自己新建一个，在里面写上如下，表示这些类型文件不需要git：
 ```
    .DS_Store
    Thumbs.db
    db.json
    *.log
    node_modules/
    public/
    .deploy*/
```
注意，如果你之前克隆过theme中的主题文件，那么应该把主题文件中的.git文件夹删掉，因为git不能嵌套上传，最好是显示隐藏文件，检查一下有没有，否则上传的时候会出错，导致你的主题文件无法上传，这样你的配置在别的电脑上就用不了了。




- 上传文件
```
git add .
git commit –m "add branch hexo"
git push
```
这样就上传完了，可以去你的github上看一看hexo分支有没有上传上去，其中`node_modules`、`public`、`db.json`已经被忽略掉了，没有关系，不需要上传的，因为在别的电脑上需要重新输入命令安装 。


最后去github 上查看 `hexo`下的分支就会发现多了好多本地源文件，这就证明已经上传成功了。



## 四：跟换电脑操作

```
# 安装GIT
sudo apt-get install git

# 设置git 全局邮箱和用户名
git config --global user.name   "imtudou"
git config --global user.email  "imtudous@163.com"

# 设置SSH KEY
ssh-keygen -t rsa -C "youremail"
#生成后填到github和coding上（有coding平台的话）
#验证是否成功
ssh -T git@github.com
ssh -T git@git.coding.net #(有coding平台的话)

# 安装node.js
sudo apt-get install nodejs
sudo apt-get install npm

#  安装hexo
sudo npm install hexo-cli -g

直接在任意文件夹下，git clone git@………………

然后进入克隆到的文件夹：cd xxx.github.io
npm install
npm install hexo-deployer-git --save

生成，部署：hexo g
hexo d

然后就可以开始写你的新博客了 hexo new newpage

Tips:不要忘了，每次写完最好都把源文件上传一下
git add .
git commit –m "xxxx"
git push

如果是在已经编辑过的电脑上，已经有clone文件夹了，那么，每次只要和远端同步一下就行了
git pull

```

<font style="color:red">注意每次先 git pull（拉取） 后在git push（推送）<font>



[知乎原文](https://www.zhihu.com/question/21193762)

