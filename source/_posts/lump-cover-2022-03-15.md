---
title: 设置文章封面背景色
katex: false
mathjax: false
cover: false
tags: tutorial
categories: []
date: 2022-03-15 00:21:22
updated: 2022-03-15 00:21:22
---
## 用途

当文章没有设置封面(`cover:false`)时，可设置从指定颜色中随机展示文章页标题背景色和上/下一篇文章背景色

注意：*因文章标题背景色有灰度处理，比设置的颜色深*

## 配置

配置文件`cover`下新增节点`lump`为颜色列表。

```yml
cover:
  lump:
    - "#722ed1"
    - "#1890ff"
    - "#FF9E80"
    - "#7cb305"
```
