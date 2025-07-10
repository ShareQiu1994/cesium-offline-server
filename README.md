# cesium-offline-server V1.1.6

● 主要功能

1. 发布地图服务 cesiumlab 输出的紧凑型文件 .pak  以及标注的 .mbtiles .db (地图发布为标准的XYZ/TMS服务,支持CesiumJS、Cesium For UE/Unity、MapboxGL、Leaflet、Openlays、QGIS、ArcgisPro、GlobalMapper等使用)
2. 发布地形服务 cesiumlab 输出的紧凑型文件 .pak  (地形发布为标准的Cesium服务和MapBoxRGB服务,支持CesiumJS、Cesium For UE/Unity、MapboxGL等使用)
4. 发布模型服务 cesiumlab 输出的紧凑型文件 .clt  (模型服务发布为标注的3dtiles服务,支持CesiumJS、Cesium For UE/Unity等使用  )
5. 发布的服务支持 jwt 鉴权
6. 支持 http/https
7. 支持 通过 config 配置文件配置系统参数

● 使用手册

1. 将下载输出的地图 .mbtiles .pak 文件存储于 sqlite/map
2. 将下载输出的地形 .pak 文件存储于 sqlite/terrain
3. 将下载输出的模型 .clt 文件存储于 sqlite/tileset
4. 执行 CeisumOfflineServer 启动文件
5. 访问 http://127.0.0.1 查看示例代码

● config 配置项

```javascript
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

# 系统截图

系统运行截图：
![图片](https://devmodels.oss-cn-shenzhen.aliyuncs.com/devtest/liubofang/images/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20230801175802.png)

访问系统发布的 web 页面查看代码示例：
![图片](https://devmodels.oss-cn-shenzhen.aliyuncs.com/devtest/liubofang/images/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20230801180410.png)
![图片](https://devmodels.oss-cn-shenzhen.aliyuncs.com/devtest/liubofang/images/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20230801180357.png)

示例代码详情:
![图片](https://devmodels.oss-cn-shenzhen.aliyuncs.com/devtest/liubofang/images/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20230801175028.png)
![图片](https://devmodels.oss-cn-shenzhen.aliyuncs.com/devtest/liubofang/images/7101.png)
![图片](https://devmodels.oss-cn-shenzhen.aliyuncs.com/devtest/liubofang/images/7102.jpg)
![图片](https://devmodels.oss-cn-shenzhen.aliyuncs.com/devtest/liubofang/images/7103.jpg)
![图片](https://devmodels.oss-cn-shenzhen.aliyuncs.com/devtest/liubofang/images/7104.jpg)
![图片](https://devmodels.oss-cn-shenzhen.aliyuncs.com/devtest/liubofang/images/7105.jpg)
![图片](https://devmodels.oss-cn-shenzhen.aliyuncs.com/devtest/liubofang/images/7106.jpg)


# windows & linux DownLoad

https://github.com/ShareQiu1994/cesium-offline-server/releases/tag/1.1.6

