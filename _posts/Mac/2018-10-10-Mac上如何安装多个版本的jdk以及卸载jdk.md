---
title: mac上如何安装多个版本的jdk以及卸载jdk
date: 2018-10-10 03:33:00
tags: 
- Mac
category: 
- Mac
description: mac上如何安装多个版本的jdk以及卸载jdk
---
<!-- image url 
https://raw.githubusercontent.com/HealerJean/HealerJean.github.io/master/blogImages
　　首行缩进
<font color="red">  </font>
-->

## 前言

### 1、直接安装
####  dmp包直接安装两个版本的jdk，比如我这里安装的`1.8.0_181` 、`10.0.2`。

![WX20181009-112351@2x](https://raw.githubusercontent.com/HealerJean/HealerJean.github.io/master/blogImages/WX20181009-112351@2x.png)

### 2、配置环境

打开环境变量配置文件`bash_profile `


```
vim ~/.bash_profile 


# java
export JAVA_8_HOME="/Library/Java/JavaVirtualMachines/jdk1.8.0_181.jdk/Contents/Home"
export JAVA_10_HOME="/Library/Java/JavaVirtualMachines/jdk-10.0.2.jdk/Contents/Home"

alias jdk8="export JAVA_HOME=$JAVA_8_HOME"
alias jdk10="export JAVA_HOME=$JAVA_10_HOME"

export JAVA_HOME=$JAVA_8_HOME
export PATH="$JAVA_HOME:$PATH"


source ~/.bash_profile

```

### 3、任意切换java环境
#### 控制台输入jdk8或者jdk10就会自动切换


```
JeandeMBP:~ healerjean$ jdk8
JeandeMBP:~ healerjean$ java -version
java version "1.8.0_181"
Java(TM) SE Runtime Environment (build 1.8.0_181-b13)
Java HotSpot(TM) 64-Bit Server VM (build 25.181-b13, mixed mode)



JeandeMBP:~ healerjean$ jdk10
JeandeMBP:~ healerjean$ java -version
java version "10.0.2" 2018-07-17
Java(TM) SE Runtime Environment 18.3 (build 10.0.2+13)
Java HotSpot(TM) 64-Bit Server VM 18.3 (build 10.0.2+13, mixed mode)

```


## 4、删除jdk


```
输入 
sudo rm -fr /Library/Internet\ Plug-Ins/JavaAppletPlugin.plugin  sudo rm -fr /Library/PreferencesPanes/JavaControlPanel.prefpane


查找当前版本  输入：ls /Library/Java/JavaVirtualMachines/ 
输出：jdk1.8.0_181.jdk

sudo rm -rf /Library/Java/JavaVirtualMachines/jdk1.8.0_181.jdk



```


<font color="red"> 感兴趣的，欢迎添加博主微信， </font>哈，博主很乐意和各路好友交流，如果满意，请打赏博主任意金额，感兴趣的在微信转账的时候，备备注您的微信或者其他联系方式。添加博主微信哦。
<br/>
请下方留言吧。可与博主自由讨论哦

|支付包 | 微信|微信公众号|
|:-------:|:-------:|:------:|
|![支付宝](https://raw.githubusercontent.com/HealerJean/HealerJean.github.io/master/assets/img/tctip/alpay.jpg) | ![微信](https://raw.githubusercontent.com/HealerJean/HealerJean.github.io/master/assets/img/tctip/weixin.jpg)|![微信公众号](https://raw.githubusercontent.com/HealerJean/HealerJean.github.io/master/assets/img/my/qrcode_for_gh_a23c07a2da9e_258.jpg)|




<!-- Gitalk 评论 start  -->

<link rel="stylesheet" href="https://unpkg.com/gitalk/dist/gitalk.css">
<script src="https://unpkg.com/gitalk@latest/dist/gitalk.min.js"></script> 
<div id="gitalk-container"></div>    
 <script type="text/javascript">
    var gitalk = new Gitalk({
		clientID: `1d164cd85549874d0e3a`,
		clientSecret: `527c3d223d1e6608953e835b547061037d140355`,
		repo: `HealerJean.github.io`,
		owner: 'HealerJean',
		admin: ['HealerJean'],
		id: '3iLbrBRsYwpG4yUg',
    });
    gitalk.render('gitalk-container');
</script> 

<!-- Gitalk end -->

