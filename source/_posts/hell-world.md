---
title: share hexo
date: 2019-09-27 11:51:49
tags: 
	 - 个人搭建hexo博客遇到的坑
declare: true
---
## hexo搭建博客成功的第一步
环境，工具：git:2.23.0.windows.1，node.js：node->v10.16.0;npm->6.9.0


## hexo搭建本人遇到的一些问题
由于本人是在windows下搭建，第一个很直观的感受是不用外网的话，下载速度足够你去玩一局游戏了，半个小时那种（有点儿夸张）；
### 1.使用前确保本地有一个能和github连接的git仓库
本人使用的是ssh，所以先需要配置你自己的ssh，这个不知道可以百度，然后添加到github上。
### 2.使用的github仓库的名必须是你account的用户名.github.io，否则无法连接。

### 3.在hexo中配置_config.yml文件时，注意！type: 后接一个空格repo： 和branch： 也一样

### 4.还有repo： 后使用的为你自己的仓库ssh地址
如：git@github.com:liuxianan/liuxianan.github.io.git

## 这就是本人在配置时遇到的一些问题，如有疑问，欢迎订阅我的公众号：程序猿成长集中地，大家一起学起！！！
