---
weight: 102
title: API Reference

search: true
---

# 其它证照识别

## 护照 OCR

护照OCR字段识别

> 代码示例：

```curl
curl --location --request POST 'https://api.aisolution.credit/v1/ocr_ppt' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'img=BASE64_ENCODE_VALUE'
```

> 护照的识别样例

```json
{
    "status":"OK",
    "message":{
        "nationality": "中国/CHINESE",
        "cType": "P",
        "countryCode": "CHN",
        "passportNo": "E45999999",
        "nameZh": "张三",
        "nameEn": "ZHANG, SAN",
        "gender": "男/M",
        "birthDate": "03 MAR 1993",
        "issueDate": "12 3月/MAR 2015",
        "expiryDate": "11 3月/MAR 2025",
        "birthPlace": "北京/BEIJING",
        "issuePlace": "辽宁/LIAONING",
        "authority": "公安部出入境管理局",
        "pNo": "459999999"
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

`POST https://api.aisolution.credit/v1/ocr_ppt`

### 请求参数

参数 | 描述
--------- | -------
`img` | `字符串`，base64编码的身份证照片，建议图片小于200KB，这样会在2秒内返回，否则返回时间较长。

### 返回数据格式

参数 | 描述
--------- | -------
`status` | 状态码
`message` | `nationality`: 国籍，`可能为空`
 | `countryCode`: 国家码，`可能为空`
 | `passportNo`: 护照号，`可能为空`
 | `nameZh`: 中文姓名，`可能为空`
 | `nameEn`: 英文姓名，`可能为空`
 | `gender`: 性别，`可能为空`
 | `birthDate`: 出生日期，`可能为空`
 | `issueDate`: 签发时间，`可能为空`
 | `expiryDate`: 失效时间，`可能为空`
 | `birthPlace`: 出生地，`可能为空`
 | `issuePlace`: 签发地，`可能为空`
 | `authority`: 颁发机构，`可能为空`
 | `cType`: 卡片类型，`可能为空`
 | `pNo`: 卡号，`可能为空`

## 海员证 OCR

海员证OCR字段识别

> 代码示例：

```curl
curl --location --request POST 'https://api.aisolution.credit/v1/ocr_smb' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'img=BASE64_ENCODE_VALUE'
```

> 识别成功返回样例

```json
{
    "status":"OK",
    "message":{
        "nationality": "中国/CHINESE",
        "countryCode": "CHN",
        "seafarerNo": "A01099999",
        "nameZh": "张三",
        "nameEn": "LIU JIAWEI",
        "gender": "男/M",
        "cType": "S",
        "birthDate": "22 MAR 1991",
        "issueDate": "07 AUG 2019",
        "expiryDate": "07 AUG 2024",
        "birthPlace": "北京/BEIJING",
        "authority": "中华人民共和国辽宁海事局"
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

`POST https://api.aisolution.credit/v1/ocr_smb`

### 请求参数

参数 | 描述
--------- | -------
`img` | `字符串`，base64编码的身份证照片，建议图片小于200KB，这样会在2秒内返回，否则返回时间较长。

### 返回数据格式

参数 | 描述
--------- | -------
`status` | 状态码
`message` | `nationality`: 国籍，`可能为空`
 | `countryCode`: 国家码，`可能为空`
 | `seafarerNo`: 海员号，`可能为空`
 | `nameZh`: 中文名，`可能为空`
 | `nameEn`: 英文名，`可能为空`
 | `gender`: 性别，`可能为空`
 | `cType`: 卡片类型，`可能为空`
 | `birthDate`: 出生日期，`可能为空`
 | `issueDate`: 签发日期，`可能为空`
 | `expiryDate`: 失效日期，`可能为空`
 | `birthPlace`: 出生地，`可能为空`
 | `authority`: 颁发机构，`可能为空`

## 船员服务簿 OCR

船员服务簿OCR字段识别

> 代码示例：

```curl
curl --location --request POST 'https://api.aisolution.credit/v1/ocr_sbr' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'img=BASE64_ENCODE_VALUE'
```

> 识别成功返回样例

```json
{
    "status":"OK",
    "message":{
	"name": "张三",
	"registerNo": "230123199103032090",
	"printNo": "01611666",
	"sbrNo": "0161166",
	"issueDate": "2015-05-04",
	"authority": "中华人民共和国海事局"
    }
}
```

```json
{
    "status":"OK",
    "message":{
	"nationality": "中国",
	"nameZh": "张三",
	"nameEn": "LiuJiawei",
	"registerNo": "230123199103033333",
	"printNo": "23012333",
	"sbrNo": "2301233",
	"birthDateZh": "1991年03月03日",
	"birthDateEn": "Mar 03, 1991",
	"issueDateZh": "2015年05月04日",
	"issueDateEn": "May 04, 2015",
	"authority": "中华人民共和国大连海事局"

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

`POST https://api.aisolution.credit/v1/ocr_sbr`

### 请求参数

参数 | 描述
--------- | -------
`img` | `字符串`，base64编码的身份证照片，建议图片小于200KB，这样会在2秒内返回，否则返回时间较长。

### 返回数据格式

参数 | 描述
--------- | -------
`status` | 状态码
`message` | `name`: 姓名，`可能为空` 
 | `registerNo`: 注册号，`可能为空`
 | `printNo`: 服务簿印刷号，`可能为空`
 | `sbrNo`: 编号，`可能为空`
 | `issueDate`: 签发日期，`可能为空`
 | `authority`: 颁发机构，`可能为空`
 | `nationality`: 国家，`可能为空`
 | `nameZh`: 中文名，`可能为空`
 | `nameEn`: 英文名，`可能为空`
 | `birthDateZh`: 中文出生日期，`可能为空`
 | `birthDateEn`: 英文出生日期，`可能为空`
 | `issueDateZh`: 中文签发日期，`可能为空`
 | `issueDateEn`: 英文签发日期，`可能为空`
 | `authority`: 颁发机构，`可能为空`


## 台塑海运ECDIS OCR

台塑海运ECDIS OCR字段识别

> 代码示例：

```curl
curl --location --request POST 'https://api.aisolution.credit/v1/ocr_fpmc' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'img=BASE64_ENCODE_VALUE'
```

> 识别成功返回样例

```json
{
    "status":"OK",
    "message":{
	"ctype": "FPMC",
	"name": "ZHANG SAN",
	"courseNumber": "ECDIS01",
	"trainDays": "2 days",
	"courseTitle": "FURUNO ECDIS Type Specific Training Course",
	"certificateNo": "KS00666",
	"birthDate": "MAR.03, 1991",
	"issueDate": "MAR.16, 2017",
	"content": "Familiarization with available function, Familiarization with the menu structure, Display setup, Setting of safety values, Recognition of the alarms and malfunction indicators and the action to be taken, Route planning, Route monitoring, Changing over to backup systems, Loading charts and licenses, Updating of software",
	"operationalModel": "FMD - xx00",
	"courseStartDate": "MAR 15,2017",
	"courseEndDate": "MAR 16,2017"
    }
}
```

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

`POST https://api.aisolution.credit/v1/fpmc`

### 请求参数

参数 | 描述
--------- | -------
`img` | `字符串`，base64编码的身份证照片，建议图片小于200KB，这样会在2秒内返回，否则返回时间较长。

### 返回数据格式

参数 | 描述
--------- | -------
`status` | 状态码
`message` | `ctype`: 卡片类型，`可能为空`
 | `name`: 姓名，`可能为空`
 | `courseNumber`: 课程编号，`可能为空`
 | `trainDays`: 培训天数，`可能为空`
 | `courseTitle`: 培训科目，`可能为空`
 | `certificateNo`: 证书编号，`可能为空`
 | `birthDate`: 出生日期，`可能为空`
 | `issueDate`: 签发日期，`可能为空`
 | `content`: 培训内容，`可能为空`
 | `operationalModel`: 培训模式，`可能为空`
 | `courseStartDate`: 课程开始时间，`可能为空`
 | `courseEndDate`: 课程结束时间，`可能为空`

## 巴拿马登船证 OCR

巴拿马登船证OCR字段识别

> 代码示例：

```curl
curl --location --request POST 'https://api.aisolution.credit/v1/ocr_panama' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'img=BASE64_ENCODE_VALUE'
```

> 识别成功返回样例一

```json
{
    "status":"OK",
    "message":{
	"ctype": "XU",
	"countryCode": "PAN",
	"nationality": "CHINESE",
	"name": "SAN ZHANG",
	"gender": "M",
	"seamanBook": "P0567777",
	"idNumber": "E31404777",
	"seafarerId": "500429953",
	"birthDate": "17-09-1980",
	"birthPlace": "BEIJING",
	"issueDate": "18-03-2020",
	"expiryDate": "12-11-2024",
	"regional": "HO CHI MINH",
	"level": "SUPPORT",
	"capacity": "COOK MLC 2006, Standard 3.2.4"
    }
}
```

> 识别成功返回样例二

```json
{
    "status":"OK",
    "message":{
	"ctype": "COURSES ENDORSEMENT CERTIFICATE",
	"nationality": "CHINA / CHINESE",
	"name": "SAN ZHANG",
	"no": "000976888",
	"specialDuty": "SECURITY AWARENESS TRAINING FOR ALL SEAFARERS, REG. VI8, PAR. 1-3, SEC. A-VIS, TABLE A-VI/6-1 (IMO 3.27)",
	"birthDate": "17/09/1980",
	"issueDate": "18/03/2020",
	"expiryDate": "12/11/2024"
    }
}
```

> 识别成功返回样例三

```json
{
    "status":"OK",
    "message":{
	"ctype": "COURSES ENDORSEMENT CERTIFICATE",
	"nationality": "CHINA / CHINESE",
	"name": "SAN ZHANG",
	"no": "000976666",
	"specialDuty": "SHIPS COOK COURSE, IN ACCORDANCE WITH MLC 2006, STANDARD 3.2.4 OR ILO 69",
	"birthDate": "03/03/1980",
	"issueDate": "18/03/2020",
	"expiryDate": "02/06/2021"
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

`POST https://api.aisolution.credit/v1/ocr_panama`

### 请求参数

参数 | 描述
--------- | -------
`img` | `字符串`，base64编码的身份证照片，建议图片小于200KB，这样会在2秒内返回，否则返回时间较长。

### 返回数据格式

参数 | 描述
--------- | -------
`status` | 状态码
`message` | `ctype`: 卡片类型，`可能为空`
 | `countryCode`: 国家码，`可能为空`
 | `nationality`: 国家，`可能为空`
 | `name`: 姓名，`可能为空`
 | `gender`: 性别，`可能为空`
 | `seamanBook`: 海员薄，`可能为空`
 | `idNumber`: 证书ID，`可能为空`
 | `seafarerId`: 出啊元编号，`可能为空`
 | `birthDate`: 出生日期，`可能为空`
 | `birthPlace`: 出生地，`可能为空`
 | `regional`: 区域，`可能为空`
 | `level`: 等级，`可能为空`
 | `capacity`: 技能，`可能为空`
 | `ctype`: 卡片类型，`可能为空`
 | `no`: 技能科目编号，`可能为空`
 | `ctype`: 卡片类型，`可能为空`
 | `specialDuty`: 技能，`可能为空`
 | `issueDate`: 签发日期，`可能为空`
 | `expiryDate`: 失效日期，`可能为空`

