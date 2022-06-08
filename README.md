# wordpress-docker-compose

> wordpress docker compose

## 启动
```
docker-compose up
```

## 同步媒体文件
> 同步博客远程媒体文件到本地

```
rsync -av sobird@sobird.me:/home/web/blog/wp-content/uploads/ src/wp-content/uploads
```