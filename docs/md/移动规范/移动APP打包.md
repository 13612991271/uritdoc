### 1、CapacitorAPI

[Capacitor Plugins - Capacitor (capacitorjs.com)](https://capacitorjs.com/docs/plugins)

### 2、Capacitor CLI 

如何使用APK打包

[CLI Reference - Capacitor (capacitorjs.com)](



### 3、APK编译配置

front\android\app\src\main\assets\capacitor.config.json

使用外部URL打包方式

```
{
   "appId": "com.urit.inv",
   "appName": "物料管理",
   "bundledWebRuntime": false,
   "server": {
      "url": "http://192.168.31.153:5656/",
      "cleartext": true
   }
}
```



前端嵌入APP打包方式

```
{
   "appId": "com.urit.inv",
   "appName": "物料管理",
   "bundledWebRuntime": false,
   "webDir":"dist",
   "server": {
      "cleartext": true
   }
}
```



### 4、APK桌面图标替换

```
在AndroidManifest.xml里面修改桌面图标路径，然后放入即可
android:icon="@drawable/ic_launcher"
```



https://capacitorjs.com/docs/cli)