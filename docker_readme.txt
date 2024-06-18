查看正在运行的容器：sudo docker container ls
查看所有的容器：sudo docker container ls -a

获取镜像：sudo docker pull mingruiye/contour-context
查看镜像列表：sudo docker image ls
可视化界面权限：xhost +
由镜像实例化容器：sudo docker run -it -v /home/lang/docker_data:/data --group-add video --volume=/tmp/.X11-unix:/tmp/.X11-unix  --env="DISPLAY=$DISPLAY" --env="QT_X11_NO_MITSHM=1" --name=contour-context mingruiye/contour-context:latest  /bin/bash
退出容器：exit
启动容器：sudo docker start -ia 7d1(container id)
启动sublime：subl filename
其他端口进入该容器: sudo docker exec -it 容器id /bin/bash

将一个容器打包为一个镜像：sudo docker commit -a ZikangYuan -m shenshaojie 7d156b67fce0 contour-context:1.0
(-a ZikangYuan:用户名 -m shenshaojie:描述 7d156b67fce0:容器ID contour-context:1.0:打包后镜像的名字及版本)
登录docker官网：sudo docker login
设置TAG为最新：sudo docker tag contour-context:1.0 mingruiye/contour-context
(contour-context:1.0:原镜像名 mingruiye/contour-context:更新后的镜像名)
发布到官网：sudo docker push mingruiye/contour-context:latest

从零开始创建一个容器：sudo docker run ubuntu

删除容器：sudo docker container rm CONTAINER-ID
(ID可通过sudo docker container ls -a查看)
删除镜像：sudo docker image rm IMAGE-ID -f
(ID可通过sudo docker image ls删除，务必先删容器，后删镜像！)
