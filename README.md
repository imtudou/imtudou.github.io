### HEXO + GITHUB 搭建个人博客相关描述
+ 首先 `npm install hexo --save` 
+ hexo 分支为博客源码库
+ master 为通过 ```hexo d```命令发布到```xxx.github.io```仓库里的是发布文件

###  HEXO 相关命令
1. 安装hexo
```sudo npm install hexo-cli -g```
2. 新建文章
```hexo new xxx``` 会看见在在根目录对应的```source/_posts/```文件里有一个对应的.md文件
3. 发布前先清除缓存数据
```hexo clean```
4. 生成 
```hexo g```
5. 部署
```hexo d```

### GITHUB 相关配置