# cesium-offline-server V1.2

● 主要功能

1. 发布地型服务 cesiumlab 输出的地形紧凑型文件 .pak
2. 发布地图服务 爬虫下载的紧凑型文件 .mbtiles 以及 cesiumlab 输出的 .pak
3. 发布模型服务 cesiumlab 输出的 3dtiles 紧凑型文件 .clt
4. 发布的服务支持 jwt 鉴权
5. 支持 http/https

● 使用手册

1. 将下载输出的地图 .mbtiles .pak 文件存储于 sqlite/map
2. 将下载输出的地形 .pak 文件存储于 sqlite/terrain
3. 将下载输出的模型 .clt 文件存储于 sqlite/tileset
4. 执行 CeisumOfflineServer 启动文件

# windows & linux DownLoad

https://github.com/ShareQiu1994/cesium-offline-server/releases/tag/1.2

# Docker:

拉取镜像命令：

```
docker pull 15819588170/cesium-offline-server
```

启动容器命令:

```
docker run --name cesium-offline-server  -p 3000:3000 -p 443:443 -v D:/xxx/map:/usr/local/home/sqlite/map -v D:/xxx/terrain:/usr/local/home/sqlite/terrain -v D:/xxx/tileset:/usr/local/home/sqlite/tileset -v D:/xxx/tile:/usr/local/home/tile -v D:/xxx/key:/usr/local/home/key -itd 15819588170/cesium-offline-server:latest
```

## docker 主要参数

### 宿主机端口映射

#### -p xxx:3000 http 端口

#### -p xxx:443 https 端口

### 宿主机目录挂载

#### -v D:/xxx/map:/usr/local/home/sqlite/map 地图文件 (.mbtiles .pak)

#### -v D:/xxx/terrain:/usr/local/home/sqlite/terrain 地形文件 (.pak)

#### -v D:/xxx/tileset:/usr/local/home/sqlite/tileset 模型文件 (.clt)

#### -v D:/xxx/key:/usr/local/home/sqlite/key SSL 证书文

#### -v D:/xxx/tile:/usr/local/home/tile 散列文件
