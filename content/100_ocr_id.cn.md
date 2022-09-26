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

## 身份证 OCR

身份证OCR字段识别

> 代码示例：

```curl
curl --location --request POST 'https://api.aisolution.credit/v1/ocr_cn' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'img=BASE64_ENCODE_VALUE'
```

> 身份证正面的识别样例

```json
{
    "status":"OK",
    "message":{
        "identityNo": "6123221985032345",
        "name": "张三",
        "gender": "男",
        "ethnic": "汉",
        "birthDate": "1993年3月03日",
        "birthPlace": "北京市海淀区学院路219号1-1"
    }
}
```

> 身份证反面的识别样例

```json
{
    "status":"OK",
    "message":{
        "nationality": "中华人民共和国",
        "cType": "居民身份证",
        "authority": "北京市公安局海淀分局",
        "effectiveDate": "2014.09.25-2034.09.25"
    }
}
```


> 图片识别失败样例

```json
{
  "status": "FAIL",
  "message": "check input image and retry"
}
```

> 请求参数错误

```json
{
  "status": "INVALID_REQUEST",
  "message": "check request params"
}
```

> 上传的图片格式错误应答样例

```json
{
  "status": "IMAGE_INVALID_FORMAT",
  "message": "image format not support"
}
```

> 照片超过2M应答样例

```json
{
  "status": "IMAGE_INVALID_SIZE",
  "message": "image larger than 2M"
}
```

> 服务器内部错误

```json
{
    "status": "RETRY_LATER",
    "message": "Service is not available right now, please try again later"
}
```

### HTTP请求

`POST https://api.aisolution.credit/v1/ocr_cn`

### 请求参数
参数 | 描述
--------- | -------
`img` | `字符串`，base64编码的身份证照片，建议图片小于200KB，这样会在2秒内返回，否则返回时间较长。

### 返回数据格式

参数 | 描述
--------- | -------
`status` | 状态码
`message` | `identityNo`：身份证号码，`可能为空`
 | `name`：姓名，`可能为空`
 | `gender`：性别，`可能为空`
 | `ethnic`：种族，`可能为空`
 | `birthDate`：出生日期，`可能为空`
 | `birthPlace`：出生地，`可能为空`
 | `nationality`：国籍，`可能为空`
 | `cType`：卡片类型，`可能为空`
 | `authority`：颁发机构，`可能为空`
 | `effectiveDate`：有效期，`可能为空`

