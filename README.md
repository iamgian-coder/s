1、在mapbox中添加一个自定义的layer,renderingMode:3d，在onAdd中实例化THREE   
 id: "THREE",
 type: "custom",
 renderingMode: "3d",

2、在mapbox中还添加了一个天空盒子
id: "skybox",
type: "custom",
renderingMode: "3d",

syncMapboxToTHREE

cesium三维地图

setHTML是锚点的主要方法

修改mapbox源码支持不同的坐标系，mapbox默认支持的投影是3857（web墨卡托？）但是实际应用中我们经常会使用高德、百度、天地图的服务，原生mapbox是不支持的，需要我们修改源码以支持以上坐标系。

mapboxgl对地图服务坐标系的要求仅仅是EPSG:3857，也就是web墨卡托投影。如果你的地图服务是此之外的坐标系，你需要另找扩展或自己去写插件了。如果你使用的是cgcs2000(国家2000、4490)的坐标系，可以参考下面这个扩展，本人测试过，geoserver发布的矢量切片、arcgis 栅格切片、arcgis 动态图服务，都是可以的。（https://zhuanlan.zhihu.com/p/141725135）
