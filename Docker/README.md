# <center>Docker命令</center>

#### 1.创建镜像

docker build -t 镜像名称:版本号 .

>`docker build -t demo:v0.1 .`

>`docker run -d --name=镜像别名 --network=host --restart=always  -v 本机路径:容器路径 镜像名称:版本号`

>`docker run -d --name=pre.rs.weixinopen --network=host --restart=always  -v /root/preworkspace/demo:/app ImageName:v0.1`

#### 2.镜像容器文件拷贝

a.容器拷贝文件到宿主机

>`docker cp 容器文件路径 容器ID:宿主机文件路径`

>`docker cp /var/app/demo/views/index.html 91edca889e30:/var/app/demo/views/index.html`

>`docker cp /var/app/demo/views/index.html 91edca889e30:/var/app/demo/views/index.html`

b.宿主机拷贝文件到容器

>`docker cp 宿主机文件路径 容器ID:容器文件路径`

>`docker cp /root/workspace/jingxuebao/var/app/demo/views/ 91edca889e30:/var/app/demo/`

>`docker cp /root/workspace/jingxuebao/var/app/demo/views/index.html 91edca889e30:/var/app/demo/index.html`