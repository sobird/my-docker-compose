# my-docker-compose

> 通过docker定制本地快速部署服务，目前支持了WordPress、PHP开发环境

## 启动
```
docker-compose up
```

## WordPress

### 同步媒体文件
> 同步博客远程媒体文件到本地

```
rsync -av sobird@sobird.me:/home/web/blog/wp-content/uploads/ wordpress/wp-content/uploads
```

### 同步主题文件
> 同步博客远程主题文件到本地
```
rsync -av sobird@sobird.me:/home/web/blog/wp-content/themes/junior2011/ wordpress/wp-content/themes/junior2011
```

### 同步插件文件
> 同步博客远程插件文件到本地
```
rsync -av sobird@sobird.me:/home/web/blog/wp-content/plugins/ wordpress/wp-content/plugins
```

### 数据库导入/导出

数据导出
```
mysqldump -usobird -p wordpress > wordpress.sql
```

数据导入
```
mysql -uroot -p  wordpress > wordpress.sql
```

## docker 命令

```sh
# 查询容器信息
docker ps
docker container ls

# 查询镜像信息
docker images
docker image ls

# 运行一个容器
docker run -d --name myhttpd -p 80:80 httpd

# 进入容器执行交互式操作
docker exec -it myhttpd bash

# 查询镜像文件的分层结构
docker image history httpd

# 提交镜像修改
docker commit myhttpd httpdnew

# 删除镜像
docker image rm httpd

# 创建并运行 docker-compose.yml 中编排的容器
docker-compose up

# 停止并移除容器，网络，镜像和卷
docker-compose down

# 用于构建Docker镜像。它从Dockerfile文件中读取指令，并根据这些指令来构建镜像。
# Dockerfile是一个文本文件，其中包含了一系列的指令，用于描述如何构建Docker镜像
docker build -t httpdNew .
```

## SQL
### 替换文章内容，比如内容中的url。

```sql
UPDATE wp_posts SET post_content=REPLACE(post_content, 'http://localhost/', 'http://sobird.com/');
```