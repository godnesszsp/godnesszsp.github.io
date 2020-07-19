### 今日收获：

#### 1.今天先是把rabbitMQ了解了一下快速入门，安装和配置：（windows）

1. 去[官网下载](https://www.rabbitmq.com/download.html)rabbitMQ的的安装包，但是目前都是3.8的版本了，新版本遇到一些问题可能就比较麻烦了，所以本人是安装的3.7.7的版本。网上的解决方案大多数是3.7.x的版本的，这里我上传了一个3.7.7版本的，自行下载（链接：https://pan.baidu.com/s/11tJ4h5Xmuc2wVqQWXLU1fQ 
   提取码：4exu ）；

2. 在使用rabbitMQ之前得去配置ERLang语言，因为rabbitMQ是在ERLang的前提下开发的，只能自己去[官网下载](http://www.erlang.org/downloads)安装配置，不会自行百度；

3. 安装成功之后就是安装rabbitMQ的可视化界面了，先进入到安装目录下的sbin目录下，输入cmd，如下图所示：

   ![1595148435443](assets/1595148435443.png)

4. 然后输入安装命令rabbitmq-plugins enable rabbitmq_management

   等几秒服务起来之后就访问http://localhost:15672就可以看到可视化界面了，默认的登录账号为 guest，密码也为guest

![1595148692223](assets/1595148692223.png)

#### 2.实体机安装centos7的一些坑（u盘安装）

1.引导界面解释

界面说明：

Install CentOS 7 安装CentOS 7

Test this media & install CentOS  7 测试安装文件并安装CentOS  7

Troubleshooting 修复故障

2.在安装之前得先编辑启动盘的挂载目录或者卷标，亲测两种方式都行：

一种是网上所说的，怎么确定自己的启动盘的挂载在那儿？自行[百度](www.baidu.com)

![1595149215443](assets/1595149215443.png)

另一种是将CentOS\X207\X20X86_64 rd.live.check改为你自己启动盘的卷标名称，注意区分大小写

3.当进入到安装界面初始时安装源报错，本人试过网上说的连接网络使用阿里云镜像代理，但还是不行。

所以我就试了另一种方法，并成功了。<u>**那就是在使用UltralSO软件设置完启动盘之后，再对启动盘的根目录重新拷入一份镜像文件。**</u>在第一次进入安装源出错时它会给你一个chooes iso的按钮，到时你就可以直接选择你拷备的镜像文件了。