# cesium-offline-server V1.1.7

● 主要功能

1. **地图服务**：发布 CesiumLab 等工具输出的 .pak，以及标准 .mbtiles、.rgbtiles 等 <br/>
   - 存放目录：`sqlite/map/`；地图发布为标准 XYZ/TMS 服务，支持 CesiumJS、Cesium For UE/Unity、MapboxGL、Leaflet、OpenLayers、QGIS、ArcgisPro、GlobalMapper 等使用。
2. **地形服务**：发布 .pak、.mbtiles 等地形数据 <br/>
   - 存放目录：`sqlite/terrain/`；地形发布为标准 Cesium 服务和 MapBox RGB 服务，支持 CesiumJS、Cesium For UE/Unity、MapboxGL 等使用。
3. **三维模型（3D Tiles）服务**：发布 CesiumLab 输出的 .clt 紧凑型文件 <br/>
   - 存放目录：`sqlite/tileset/`；发布为标准 3D Tiles 服务，支持 CesiumJS、Cesium For UE/Unity 等使用。
4. **按目录组织的地图与地形（Eulee 结构）**：<br/>
   - 地图：`sqlite/euleemap/`，每个子目录为一套地图服务，以目录名作为服务名；<br/>
   - 地形：`sqlite/euleeterrain/`，每个子目录为一套地形服务，以目录名作为服务名。
5. 发布的服务支持 **JWT 鉴权**。
6. 支持 **HTTP/HTTPS**。
7. 支持通过 **config** 配置文件配置系统参数。

服务启动时会自动扫描上述目录，将符合格式的数据文件发布为可在 Cesium 中使用的瓦片或地形、模型服务；新增、删除或替换数据文件后需**重启服务**后才会在列表中生效。

● 使用手册

1. **放置数据**：将地图（.pak / .mbtiles / .rgbtiles）放入 `sqlite/map/`；地形（.pak / .mbtiles）放入 `sqlite/terrain/`；模型（.clt）放入 `sqlite/tileset/`；或按 Eulee 结构放入 `sqlite/euleemap/`、`sqlite/euleeterrain/` 对应子目录。
2. **启动服务**：执行 CesiumOfflineServer 启动文件，服务会扫描目录并发布所有符合格式的数据。
3. **访问预览**：浏览器访问 `http://127.0.0.1`（或本机 IP:端口），进入功能示例首页；首页左侧为“地图数据 / 地形数据 / 模型数据”树形列表，主区域为卡片，点击卡片可在新标签页打开对应的 Cesium 预览页（地图/地形/模型）。
4. 首页支持**技术栈切换**、**关键字搜索**过滤数据，以及**获取更多数据源**说明弹窗。

● 注意事项

- 新增、删除或替换数据文件后，需要**重启服务**，新数据才会在首页列表和预览中生效。
- 首页列表与侧栏由服务根据当前目录中的数据动态生成，无需手动配置。
- 若某类目录下没有符合格式的文件，对应分类下将不显示任何项。

● config 配置项

```javascript
{
  "http-port":80,  // http端口
  "https-port":443,  // https端口
  "open-browser": true, // 自动打开网页浏览器
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


#  CesiumOfflineServer下载地址 windows & linux

https://gitee.com/liu-bofang/cesium-offline-server/releases/tag/1.1.7

# 测试数据下载地址

通过网盘分享的文件：测试数据 香港(卫星地图/地形/城市白模)
链接: https://pan.baidu.com/s/10TaQSc4DfbCqfMI6T75NPg?pwd=j2dn 提取码: j2dn 
--来自百度网盘超级会员v6的分享

# 更多数据 全球/全国  谷歌卫星/Arcgis卫星/天地图卫星/天地图地形/天地图矢量街道/地名路网/城市白模 定制服务

请联系微信： liubf94 QQ：421419567 <br/>
淘宝商城：https://shop330354166.taobao.com/index.htm?spm=2013.1.w5002-25038922603.2.7f9e3bf0lnzAs1
