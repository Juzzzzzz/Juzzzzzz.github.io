---
layout:     post
title:      "spmat4stata: 我的第一个R包"
subtitle:   "又一个第一次..."
date:       2018-09-25 23:00:00
author:     "Ju"
header-img: "img/cam-bg1.jpg"
tags:
    - R
    - Stata
    - Package
    - Spatial
---

> 本以为写R包就是定义一个函数然后上传就完事了
>> 没想到...这么多坑！

## Motivation

暑假以来，导师一直叫我学空间计量，回归的时候需要用到空间权重矩阵，导师要求用Stata，因为这是我们团队的公共工具。

Stata15 可以直接做一些空间计量模型，因为要用到一些非地理的空间权重矩阵，所以要自己做这个矩阵，处理好数据后Stata可以从外部导入一个`txt`格式的空间权重矩阵，但是做这个文件还是挺麻烦的，于是我就想做个R包，一劳永逸。

`spmat4stata` 就诞生了。

## spmat4stata

**Installation**

```R
devtools::install_github("Juzzzzzz/spmat4stata")
```

**Usage**

现在刚刚 `v 0.1.0` 版本，只有一个函数 `long2mat` 。

主要功能：

- 把长格式的空间权重矩阵转变成矩阵格式的空间权重矩阵
- 国家或地区的`ID`如果不是整数型，可以通过设定参数 `id_is_int = FALSE` 来将字符型的 `ID` 转换成整数型 `ID`，并自动生成对照表

包内我内置了一个通过世界地图做的一个国家和地区的空间权重Queen邻接矩阵（queen_long），可以用来做一下测试：

```R
long2mat(data_long = queen_long, country_id = "Country ISO3 Code",  
         counter_id = "Counterpart Country ISO3 Code", contiguity = "Contiguity",  
         id_is_int = FALSE, W_style = "W")
```

**Task List**

- [x] Create package **`spmat4stata`**
- [x] Function: **`long2mat`** (v 0.1.0)
- [ ] Function: **`write_stata_spmat`** (v 0.2.0)
- [ ] Complete documentation (v 1.0.0)
- [ ] ...

## 关于制作包的坑

这部分就以后慢慢写吧，太累了！还要写作业...