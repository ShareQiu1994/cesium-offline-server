# cesium-offline-server V1.3

● 主要功能

1. 发布地型服务 cesiumlab 输出的地形紧凑型文件 .pak
2. 发布地图服务 爬虫下载的紧凑型文件 .mbtiles 以及 cesiumlab 输出的 .pak
3. 发布模型服务 cesiumlab 输出的 3dtiles 紧凑型文件 .clt
4. 发布的服务支持 jwt 鉴权 
5. 支持 http/https
6. 支持 通过config配置文件配置系统参数

● 使用手册

1. 将下载输出的地图 .mbtiles .pak 文件存储于 sqlite/map
2. 将下载输出的地形 .pak 文件存储于 sqlite/terrain
3. 将下载输出的模型 .clt 文件存储于 sqlite/tileset
4. 执行 CeisumOfflineServer 启动文件

● config配置项

``` javascript 
{
  "http-port":80,  // http端口
  "https-port":443,  // https端口
  "ssl-key":"server.key",   // ssl key证书文件
  "ssl-crt":"server.crt",   // ssl crt证书文件
  "jwt-token":true,         // 是否启用jwt token认证
  "jwt-username":"eulee",   // jwt登录帐号
  "jwt-password":"2023@password!.",  // jwt登录密码
  "jwt-secret-key":"liubf", // jwt密钥
  "jwt-expires-in": "1h",   // jwt token过期时间 
  "aes-key":"LBF_KEY_XU123456",  // model文件 aes 加密密钥
  "aes-iv":"LBF_KEY_XU789456"    // model文件 aes 加密密钥偏移量
}
```

# windows & linux DownLoad

https://github.com/ShareQiu1994/cesium-offline-server/releases/tag/1.3

# Docker:

拉取镜像命令：

```
docker pull 15819588170/cesium-offline-server
```

启动容器命令:

```
docker run --name cesium-offline-server  -p 80:80 -p 443:443 -v D:/xxx/map:/usr/local/home/sqlite/map -v D:/xxx/terrain:/usr/local/home/sqlite/terrain -v D:/xxx/tileset:/usr/local/home/sqlite/tileset -v D:/xxx/tile:/usr/local/home/tile -v D:/xxx/key:/usr/local/home/key -v D:/xxx/config:/usr/local/home/config -v D:/xxx/model:/usr/local/home/model -itd 15819588170/cesium-offline-server:latest
```

## docker 主要参数

### 宿主机端口映射

#### -p xxx:80 http 端口

#### -p xxx:443 https 端口

### 宿主机目录挂载

#### -v D:/xxx/map:/usr/local/home/sqlite/map 地图文件 (.mbtiles .pak)

#### -v D:/xxx/terrain:/usr/local/home/sqlite/terrain 地形文件 (.pak)

#### -v D:/xxx/tileset:/usr/local/home/sqlite/tileset 3dtiles文件 (.clt)

#### -v D:/xxx/key:/usr/local/home/sqlite/key ssl证书文件

#### -v D:/xxx/tile:/usr/local/home/tile 散列文件

#### -v D:/xxx/model:/usr/local/home/model glb/gltf文件

#### -v D:/xxx/config:/usr/local/home/config 系统配置文件
