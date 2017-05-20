---
layout:     post
title:      "在JuliaBox里运行R"
subtitle:   "不用烧电脑了orz"
date:       2017-05-20 12:00:00
author:     "Ju"
header-img: "img/post-bg-lofter004.jpg" 
tags:
    - 日志
    - R
    - JuliaBox
--- 

## **写论文！**

`DCC模型`的论文基本烂大街了，没法用啦！！

但是呢，想不出题的时候看看两个资产收益率的条件动态相关系数变化没准就会发现点什么问题。

所以呀，就要海选了！两两做，循环呀！！

![](http://ooyw340iz.bkt.clouddn.com/image/rinjuliabox/dn004.gif)

DCC要用`R`跑，跑一个DCC还是要个几秒的，要是跑几百个也是蛮烧电脑的呀！

> 云呀！现在不是什么都云了么！

部署阿里云什么的我没有账号呀！我也不会！

---

## **怎么办？**

![](http://ooyw340iz.bkt.clouddn.com/image/rinjuliabox/dn001.gif)

---

[<center><big> JuliaBox </big></center>](https://www.juliabox.com) 

<center> Run Julia from the Browser. No setup. </center> 

---

`JuliaBox`不仅可以让你在网页上做`Julia`的`Jupyter Notebooks`，它还提供一个`Linux Terminal`的`Console`，里面可以运行各种很多语言，比如`Julia`、`R`、`Python2`、`Python3`，而且里面都装好了，可能是因为`Julia`就是胶水语言吧...

> 开始吧！！

先把`R`的程序和数据准备好，压缩到一个`zip`文件里。

![](http://ooyw340iz.bkt.clouddn.com/image/rinjuliabox/juliabox001.png)
![](http://ooyw340iz.bkt.clouddn.com/image/rinjuliabox/juliabox002.png)

登录`JuliaBox`，把刚刚那个压缩包上传到一个文件夹里。

![](http://ooyw340iz.bkt.clouddn.com/image/rinjuliabox/juliabox003.png)

然后进入`Console`，界面是这样的：

![](http://ooyw340iz.bkt.clouddn.com/image/rinjuliabox/juliabox004.png)

解压然后打开`R`：

```
juser@juliabox:~$ cd R_zzz  
juser@juliabox:~/R_zzz$ unzip DCC_xxx.zip  

juser@juliabox:~/R_zzz$ cd DCC_xxx 
juser@juliabox:~/R_zzz/DCC_xxx$ R
```

---

在`R`中装好需要的包就开始跑吧：

```R
install.packages(c("ccgarch", "ggplot2"))

system.time(source("DCC_GI.R"))
```

![](http://ooyw340iz.bkt.clouddn.com/image/rinjuliabox/juliabox005.png)

因为我的目的是每个DCC输出一个图，为了好看还是用`ggplot2`画的...

所以，这个程序肯定是**贼慢**啦！！

等的时候就休息一下好了。

![](http://ooyw340iz.bkt.clouddn.com/image/rinjuliabox/dn005.gif)

---

![(http://ooyw340iz.bkt.clouddn.com/image/rinjuliabox/juliabox006.png)]

跑了120组，用了将近45分钟...

接下来就是把输出的图片打包下载下来了：

```
juser@juliabox:~/R_zzz/DCC_xxx$ zip -r img_DCC_GI.zip img_DCC_GI   
```

点一下就能下载了：

![](http://ooyw340iz.bkt.clouddn.com/image/rinjuliabox/juliabox007.png)

> 完成！

![](http://ooyw340iz.bkt.clouddn.com/image/rinjuliabox/dn003.gif)

> JuliaBox的开发者估计气死了Zzz
>> 我会好好学Julia的-。-

[![Julia](http://ooyw340iz.bkt.clouddn.com/image/rinjuliabox/juliabox008.jpg)](http://baike.baidu.com/link?url=KfpL5xeXNIYSfj0l2OwJ5jIEuVrMLi7qbRJCTpIYFWC22ymOeYSG7grtj9FvRU9P8wkRzUGtKiSkv_H_Zw-50uw5ehYcqrUy0gTGkmsZYTSLOtSFxq5oID4xF0nXxKF_WtA7Ou16dcWls0Iz_-1KNa)



