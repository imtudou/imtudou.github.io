---
title: Hexo博客NexT主题美化之顶部加载进度条
date: 2019-08-09 13:38:54
tags: hexo
categories: 随笔
---

#### 1.转到NexT目录
```js
cd themes/next
```

#### 2.获取模块
```
git clone https://github.com/theme-next/theme-next-pace source/lib/pace
```

#### 3.设置
在NexT _config.yml文件中启用模块并选择您的主题：
```js
pace:
  enable: true
  # Themes list:
  # big-counter | bounce | barber-shop | center-atom | center-circle | center-radar | center-simple
  # corner-indicator | fill-left | flat-top | flash | loading-bar | mac-osx | material | minimal
  theme: minimal
```

#### 参考
[GITHUB地址](https://github.com/theme-next/theme-next-pace)

[简书地址](https://www.jianshu.com/p/d08513d38786)
