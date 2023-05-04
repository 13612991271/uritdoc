## Excel文件下载实现方法

###### 项目实现代码：参考订单系统“导出报表”功能

##### 后端：

```
	c.Header("response-type", "blob") //必须设置响应类型为blob
	data, err := ioutil.ReadFile(path) //获取字节流
	if err != nil {
		return
	}
	c.Data(http.StatusOK, "application/vnd.ms-excel", data)
```



##### 前端：

```
    doExportOrders(params).then(res =>{
        let blob = new Blob([res], { type: "application/vnd.ms-excel" });
        // // 创建URL对象，并将Blob对象存储到URL对象中
        const url = URL.createObjectURL(blob);
        // 创建a标签元素，设置href属性和download属性
        const link = document.createElement('a');
        link.href = url;
        link.download = 'test.xlsx';
        // 模拟用户点击a标签元素进行下载
        document.body.appendChild(link);
        link.click();
        document.body.removeChild(link);
        // 释放URL对象
        URL.revokeObjectURL(url);
    })
      
```

```
//axios请求
export function doExportOrders(params) {
    return axios({
        url: "api/orders/export",
        data: params,
        responseType: "blob", //必须设置响应类型为blob
        method: "post",
    })
}
```

