# cesium-offline-server V1.0

● 主要功能

1. 发布地型服务 cesiumlab 输出的地形紧凑型文件 .pak
2. 发布地图服务 爬虫下载的紧凑型文件 .mbtiles 以及 cesiumlab 输出的 .pak
3. 发布模型服务 cesiumlab 输出的 3dtiles 紧凑型文件 .clt
4. 支持 http/https

● 使用手册

1. 将下载输出的地图 .mbtiles .pak 文件存储于 sqltie/map
2. 将下载输出的地形 .pak 文件存储于 sqltie/terrain
3. 将下载输出的模型 .clt 文件存储于 sqltie/tileset
4. 执行 CeisumOfflineServer 启动文件

# windows

https://github.com/ShareQiu1994/cesium-offline-server/releases/download/1.0/CeisumOfflineServer-Win-1.0.zip

# linux

https://github.com/ShareQiu1994/cesium-offline-server/releases/download/1.0/CeisumOfflineServer-Linux-1.0.zip

# Docker:

拉取镜像命令：

```
docker pull 15819588170/cesium-offline-server
```

启动容器命令:

```
docker run --name cesium-offline-server  -p 3000:3000 -p 443:443 -v D:/xxx/map:/usr/local/home/sqltie/map -v D:/xxx/terrain:/usr/local/home/sqltie/terrain -v D:/xxx/tileset:/usr/local/home/sqltie/tileset -v D:/code/CeisumOfflineServer/tile:/usr/local/home/tile  -itd 15819588170/cesium-offline-server:latest
```

docker run --name cesium-offline-server -p 3000:3000 -p 443:443 -itd 15819588170/cesium-offline-server:latest
