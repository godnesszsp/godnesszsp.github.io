### 今日收获：

#### 1.今天把微人事所用的技术栈列举了一下：

微人事的技术栈：

1.1**后端技术栈**

1. Spring Boot
2. Spring Security
3. MyBatis
4. MySQL
5. Redis
6. RabbitMQ
7. Spring Cache
8. WebSocket

1.2**前端技术栈**

1. Vue
2. ElementUI
3. axios
4. vue-router
5. Vuex
6. WebSocket
7. vue-cli4

#### 2.今天主要是先把项目搭建起来，所以优先去学习了redis（缓存）和rabbitMQ（消息队列）的快速入门

2.1 redis的搭建和配置（windows）

1. 去官网下载redis的安装包.exe，然后傻瓜式安装就行了，环境变量需要配置？（想要方便的话可以配置，也可以不需要配置，但启动时需要进入到安装目录下的sbin目录下，然后如下图：

   ![1595146274768](assets/1595146274768.png)

   ）

2. 然后启动直接在该目录下输入启动命令redis-server.exe，启动成功如下如所示：

   ![1595146445905](assets/1595146445905.png)

#### 3.如果想要设置密码有两种方式：

1. **命令行设置密码**。

运行cmd切换到redis根目录，先启动服务端

```
>redis-server.exe
```

另开一个cmd切换到redis根目录，启动客户端

```
>redis-cli.exe -h 127.0.0.1 -p 6379
```

客户端使用config get requirepass命令查看密码

```
>config get requirepass
1)"requirepass"
2)""    //默认空
```

客户端使用config set requirepass yourpassword命令设置密码

```
>config set requirepass 123456
>OK
```

一旦设置密码，必须先验证通过密码，否则所有操作不可用

```
>config get requirepass
(error)NOAUTH Authentication required
```

使用auth password验证密码

```
>auth 123456
>OK
>config get requirepass
1)"requirepass"
2)"123456"
```

也可以退出重新登录

```
redis-cli.exe -h 127.0.0.1 -p 6379 -a 123456
```

命令行设置的密码在服务重启后失效，所以一般不使用这种方式。

2. **配置文件设置密码**

在redis根目录下找到redis.windows.conf配置文件，搜索requirepass，找到注释密码行，添加密码如下：

```
# requirepass foobared
requirepass tenny     //注意，行前不能有空格
```

重启服务后，客户端重新登录后发现

```
>config get requirepass
1)"requirepass"
2)""
```

密码还是空？

网上查询后的办法：创建redis-server.exe 的快捷方式， 右键快捷方式属性，在目标后面增加redis.windows.conf， 这里就是关键，你虽然修改了.conf文件，但是exe却没有使用这个conf，所以我们需要**手动指定**一下exe按照**修改后的conf**运行，就OK了。

所以，这里我再一次重启redis服务(指定配置文件)

```
>redis-server.exe redis.windows.conf
```

客户端再重新登录，OK了。

```
>redis-cli.exe -h 127.0.0.1 -p 6379 -a 123456
>config get requirepass
1)"requirepass"
2)"123456"
```