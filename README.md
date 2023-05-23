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


## SQL
### 替换文章内容，比如内容中的url。

```sql
UPDATE wp_posts SET post_content=REPLACE(post_content, 'http://localhost/', 'http://sobird.com/');
```