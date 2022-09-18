# <center>Docker命令</center>

#### 1.创建镜像

docker build -t 镜像名称:版本号 .

>`docker build -t demo:v0.1 .`

>`docker run -d --name=镜像别名 --network=host --restart=always  -v 本机路径:容器路径 镜像名称:版本号`

>`docker run -d --name=demo --network=host --restart=always  -v /root/preworkspace/demo:/app ImageName:v0.1`

#### 2.镜像容器文件拷贝

a.容器拷贝文件到宿主机

>`docker cp 容器文件路径 容器ID:宿主机文件路径`

>`docker cp /var/app/demo/views/index.html 91edca889e30:/var/app/demo/views/index.html`

>`docker cp /var/app/demo/views/index.html 91edca889e30:/var/app/demo/views/index.html`

b.宿主机拷贝文件到容器

>`docker cp 宿主机文件路径 容器ID:容器文件路径`

>`docker cp /root/workspace/demo/var/app/demo/views/ 91edca889e30:/var/app/demo/`

>`docker cp /root/workspace/demo/var/app/demo/views/index.html 91edca889e30:/var/app/demo/index.html`



#### Registry
>`docker run -d -v /home/registry:/var/lib/registry -p 9090:5000 --network=host --restart=always --name registry registry:latest`


#### Registry-UI



#### Gitlab-Runner

```
ps aux|grep gitlab-runner  #查看当前runner用户

sudo gitlab-runner uninstall  #删除gitlab-runner

gitlab-runner install --working-directory /home/gitlab-runner --user root   #安装并设置--user(例如我想设置为root)

sudo service gitlab-runner restart  #重启gitlab-runner

ps aux|grep gitlab-runner #再次执行会发现--user的用户名已经更换成root了
```

以下是另一种情况

Ghost，更换了服务器，用户ID发生了变化 ，需要重新安装 runner服务 以gitlab-runner用户，重新安装 了服务
`/usr/local/bin/gitlab-runner install -u gitlab-runner`
再次启动, runner
`gitlab-runner start`
看到启动正常 service running

```

Microfoft@DESKTOP-N8QRTJ4 MINGW64 ~
$ ssh-add .ssh/id_rsa
Could not open a connection to your authentication agent.

Microfoft@DESKTOP-N8QRTJ4 MINGW64 ~
$ ssh-agent bash

Microfoft@DESKTOP-N8QRTJ4 MINGW64 ~
$ ssh-add id_rsa
id_rsa: No such file or directory

Microfoft@DESKTOP-N8QRTJ4 MINGW64 ~
$ ssh-add .ssh/id_rsa
Enter passphrase for .ssh/id_rsa:
Identity added: .ssh/id_rsa (fangts@zhaoxuewang.cn)

Microfoft@DESKTOP-N8QRTJ4 MINGW64 ~
$


windows下在多个git服务器之间切换，需要使用 ssh-add.exe ~/.ssh/id_rsa_xxx 重新添加git密钥才能正常clone代码，其中“id_ras_xxx”是密钥的名字，比如本人github所用的密钥名为id_rsa_github(这里需要注意不要同公钥发生混淆，公钥名为id_rsa_github.pub)。

提示“ Could not open a connection to your authentication agent”，是因为你没有启动ssh-agent，解决方法简单：

ssh://git@你的域名:222/用户名/test.git

```
