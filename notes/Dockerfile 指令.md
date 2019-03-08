---
title: Dockerfile 指令
created: '2019-03-07T05:54:18.981Z'
modified: '2019-03-07T06:21:21.796Z'
---

# Dockerfile 指令

* RUN：指定镜像被构建时执行的命令。
* CMD：容器被启动时要执行的命令；`docker run` 命令会覆盖 `CMD` 指令。
  ```
  CMD ["/bin/bash", "-l"]
  ```
* ENTRYPOINT：类似于 CMD 指令，但是不会被覆盖，`docker run` 后门的参数会传递给 `ENTRYPOINT` 作为参数；`docker run --entrypoint` 会覆盖 `ENTRYPOINT` 命令。
  ```
  ENTRYPOINT ["/usr/sbin/nginx", "-g", "daemon off;"]
  ```
* WORKDIR：在容器内部设置工作目录，`CMD` 和 `ENTRYPOINT` 会在这个指定目录执行。
  ```
  WORKDIR /opt/webapp/db
  ```
* ENV：在镜像构建过程中设置好环境变量。
  ```
  ENV RVM_PATH /home/rvm/
  ```
* USER：指定镜像以什么用户运行。
  ```
  USER user:group
  ```
* VOLUME：

* ADD：将构建环境下的文件和目录复制到镜像中；如果将压缩文件指定为源文件，docker 会自动解压。
  ```
  ADD software.lic /opt/application/software.lic
  ```
* COPY： 类似于 `ADD`，只会复制文件或目录而不会做解压。
*
