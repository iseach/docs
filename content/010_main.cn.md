---
weight: 10
title: API Reference

search: true
---

# 概述

wenlanapi提供如图像生成文本、PM2.5数据查询、全球手机号码运营商归属地查询、中国身份证信息查询、全球银行卡信息查询等数据API接口以及提供如全语种网页文章正文抽取、文章关键词抽取、自然语言解析等基础技术API接口。

wenlanapi服务后台需要通过使用Access Key / Secret Key加密的方法来验证某个请求的发送者身份。Access Key（AK）用于标示用户，Secret Key（SK）是用户用于加密认证字符串和wenlanapi服务用来验证认证字符串的密钥，其中SK必须保密，只有用户和wenlanapi知道。

SDK初始化，需要用户先申请到属于自己的AK和SK。

> 请确保将`YOUR_ACCESS_KEY`和`YOUR_SECRET_KEY`替换为你自己的AK和SK。

<aside class="notice">
请确保将<code>YOUR_ACCESS_KEY</code>和<code>YOUR_SECRET_KEY</code>替换为你自己的AK和SK。
</aside>

# 用户认证

我们使用apiKey来认证用户，您可以在开发者门户中获取apiKey。

apiKey需要包含在所有的API请求中，请求Header如下：

`X-Api-Key: meowmeowmeow`
