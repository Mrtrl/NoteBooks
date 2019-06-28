## Gerapy 部署 scrapy爬虫

安装

```shell
# 下载gerapy
$pip install gerapy

# 下载scrapyd 用作部署
$pip install Scrapyd

# 初始化gerapy
$gerapy init

# 初始化数据库
$cd gerapy
$gerapy migrate

# 运行gerapy服务
gerapy runserver host:port

# 配置主机 -- 去到需要配置的主机处，键入scrapyd命令
$scrapyd
```







