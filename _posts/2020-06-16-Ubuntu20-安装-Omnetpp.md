---
layout:     post
title:      Ubuntu20-安装-Omnetpp5.4
subtitle:   "Ubuntu-20 安装 omnet++5.4"
date:       2020-06-16
author:     Syncw
header-img: img/post_img/linux/linux-bg.jpg
catalog: false
tags:
    - Linux
---

## Ubuntu 20 上 安装 仿真软件 omnet++ 5.4


<object data="https://www.syncw.work/img/post_img/linux/omnet/installOmnetpp.pdf" type="application/pdf" width="750px" height="750px">
    <embed src="https://www.syncw.work/img/post_img/linux/omnet/installOmnetpp.pdf" type="application/pdf">
        <p>If your browser does not support PDFs. Please download the PDF to view it: <a href="https://www.syncw.work/img/post_img/linux/omnet/installOmnetpp.pdf">Download PDF</a>.</p>
    </embed>
</object>


## 问题 & 解决

1. 安装完成后，omnet 可能会启动失败。并提示：<b>An error has occurred。See the log file</b>
	<br>
	首先，命令行终端 执行
	```
	java -version
	```
	检查 当前使用的JDK版本，很有可能是 Java 11。这就是问题所在。Omnet++5.4 不支持 Java高版本。所以要切换到 JDK8。 <br>
	命令行终端执行该命令，输入密码后回车。
	```
	sudo update-alternatives --config java
	```
	该命令会显示当前ubuntu系统中，所有可用的 JDK版本。<br>

	------
	<br>
	假设 系统中没有 JDK8。（若已有，可跳过安装JDK8的 步骤）<br>
	终端执行命令，安装JDK8
	```
	sudo apt-get update
	sudo apt-get install openjdk-8-jdk
	```
	------
	安装完成后。再次执行终端命令，切换JDK
	```
	sudo update-alternatives --config java
	```
	![jdk01](https://www.syncw.work/img/post_img/linux/omnet/jdk01.png)
	输入 序号 选择 要切换的JDK。如：2 。然后回车。
	<br>
	再次执行 <b>java -version</b> ，查看JDK 是否切换成功。<br>
	若已成功切换到 JDK8。重启omnet就可以了。
	<br>
	<br>
2. 第一次启动omnet 可能会出现提示：
	![omnet](https://www.syncw.work/img/post_img/linux/omnet/omnet01.png)
	<br>
	INET Framework 需要安装 ，第二个examples 可以取消安装。





## 后记

由于国内对 github 访问速度较慢，可能会导致 评论组件加载失败。<br>
可尝试刷新页面。若仍不能解决，可联系博主讨论解决方案。


