---
weight: 100
title: API Reference

search: true
---

# 身份证识别

## 中国身份证信息查询🆔

查询身份证的基本信息，包括发证地区、出生年月日和性别及有效性。

> 代码示例：

```python
import sdk

api = sdk.client('YOUR_ACCESS_KEY', 'YOUR_SECRET_KEY')
data = {"id": "330825197801104539"}
url = "https://api.crawler.club/idcard"
response = api.request(url, data)
print(response)
```

```php
<?php
require_once "crawlerclub/Client.php";

$client = new Client("YOUR_ACCESS_KEY", "YOUR_SECRET_KEY");
$url = "https://api.crawler.club/idcard";
$data = array("id"=>"330825197801104539");
$response = $client->request($url, $data);
print($response);
```

```java
import java.util.HashMap;
import java.util.Map;
import club.crawler.Client;

public class MainClass {
    public static void main(String[] args) {
        Client api = new Client("YOUR_ACCESS_KEY", "YOUR_SECRET_KEY");
        Map<String, String> data = new HashMap<>();
        data.put("id", "330825197801104539");
        String url = "https://api.crawler.club/idcard";
        String response = client.request(url, data);
        System.out.println(response);
    }
}
```

```go
package main

import (
    "fmt"
    "crawler.club/gosdk"
)

func main() {
    api := gosdk.NewClient("YOUR_ACCESS_KEY", "YOUR_SECRET_KEY")
    data := map[string]string{
        "id":  "330825197801104539",
    }
    url := "https://api.crawler.club/idcard"
    response, _ := api.Request(url, data)
    fmt.Println(response)
}
```

> 正确返回数据应答样例

```json
{
  "status":"ok",
  "message":{
    "id":"330825197801104539",
    "birthday":"1978-01-10T00:00:00Z",
    "gender":"male",
    "province":"浙江省",
    "city":"衢州市",
    "county":"龙游县"
  }
}
```

> 请求错误应答样例

```json
{
  "status":"fail",
  "message":"checksum not correct"
}
```

### HTTP请求

`POST https://api.crawler.club/idcard`

### 请求参数

参数 | 描述
--------- | -------
`id` | `字符串`，要查询的身份证号码

### 状态码说明

status | 说明
--------- | -------
`ok` | 查找成功
`fail` | 失败，此时`message`保存错误信息

### 身份证号码信息说明

字段 | 说明
--- | ---
id|身份证号码
birthday|出生日期
gender|性别
province|省
city|市
county|县

