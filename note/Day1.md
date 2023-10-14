用docker安装naocs

- docker拉取镜像

`docker pull nacos/nacos-server:1.2.0`

- 创建容器

`docker run --env MODE=standalone --name nacos --restart=always -d -p 8848:8848 nacos/nacos-server:1.2.0`

- Mode=standlone 单机版
- -- restart=always 开机启动
- -p 8848:8848 映射端口
- -d 创建一个守护式容器在后台运行



