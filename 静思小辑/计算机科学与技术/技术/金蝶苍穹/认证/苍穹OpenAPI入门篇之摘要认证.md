https://developer.kingdee.com/article/311461951647625216?productLineId=29&isKnowledge=2&lang=zh-CN



在上一篇文章《[苍穹OpenAPI入门篇之AccessToken认证](https://vip.kingdee.com/article/311458805903550720)》中，我们介绍了金蝶云苍穹三种认证方式中的 AccessToken 认证，本期小编为大家介绍另一种安全便捷的登录认证方式：**摘要认证**。

---



# 1   应用场景

第三方系统调用金蝶云苍穹 API 服务时，需先通过身份认证。



# 2   解决方案

金蝶云苍穹支持通过**摘要认证**进行身份认证。



## 2.1   摘要认证简介



摘要认证通过 **SHA-256** 加密算法生成摘要，保障客户端与服务端通信的内容不被第三方篡改，提高破解和报文重放攻击的难度，是一种**安全性更高**的认证方式。





## 2.2   摘要认证特点



摘要认证是基于 HTTP 基本认证的**改进**版本，其主要特点在于：当我们访问某个 URL 时，在请求中使用摘要来代替密码的传输，并且采用MD5、SHA之类的不可逆哈希算法对密码加密，增强了敏感数据在传递过程中的安全性，在一定程度上防止信息被篡改，保障通信的安全。





## 2.3   摘要认证过程原理



客户端第一次请求时，通过服务端生成**随机数**，并将该随机数放在响应头中发送回客户端。然后，客户端根据**随机数、时间戳和其他用户信息**，通过指定的加密算法生成摘要。



后续客户端在调用请求时，将摘要放在请求头中再次发送给服务器。服务器获取到摘要后，根据请求信息从数据库取出客户端密码进行相同的计算后，与得出的摘要进行对比，匹配则身份验证通过，可以进行服务调用。



具体过程原理如下图所示：









## **3 功能实现**





金蝶云苍穹的摘要认证[流程](https://www.kingdee.com/products/cosmic_process_service.html?utm_source=shequ )具体如下：



**Step1 注册第三方应用**







在金蝶云苍穹开放平台录入第三方应用的基本信息，路径为：【开发服务云】→【开放平台】→【第三方应用】。点击**摘要加密认证密钥**的“刷新”按钮，自动生成摘要加密认证key。







**Step2** **服务调用**







金蝶云苍穹可以通过Java工具类指定默认算法（SHA-256）直接生成摘要：对于**GET方式**提交的API内容，所有的验证内容均放置在url的参数中；对于**POST方式**提交的API内容，所有的验证内容放置在请求体中。



注：摘要计算公式为：HMACSHA256（query的拼接参数/请求体内容+timestamp+signatureNonce，key）。



1）**GET API** 实例



请求示例：

```json
//URL：
https://feature.kingdee.com:2024/baseline_a/kapi/sys/isc_demo_basedata_1/query?select=name,number&filter=name%20eq%20123asd&appId=TEST%C3%97tamp=2021-08-18%2014:19:08&signatureNonce=iksiertoidkwek;oitdwudysletwsuej&signature=32beeebfc277817a80b01d5787242c51ca5295f5edcf2eb9371ff367f8b487a5%C2%B6meters=select&user=17299999999&usertype=Mobile&accountId=1173910536060928000
//请求结果：
{
    "success": "true",
    "data": {
        "count": 1,
        "header": [
            {
                "name": "name",
                "caption": "名称",
                "type": "String"
            },
            {
                "name": "number",
                "caption": "编码",
                "type": "String"
            }
        ],
        "rows": [
            [
                "123asd",
                "123asd"
            ]
        ]
    }
}
```

HTTP query 查询参数说明如下：

| 传入参数       | 字段类型 | 是否必输 | 字段说明                                                     |
| -------------- | -------- | -------- | ------------------------------------------------------------ |
| select         | string   | 是       | 定义查询类服务的返回参数，如 “id”、“name”、“number” 等       |
| filter         | string   | 否       | 过滤参数、可以设置查询条件如 “filter=name eq 123asd”         |
| appId          | string   | 是       | 第三方 appId                                                 |
| timestamp      | string   | 是       | 当前时间，和服务器时间相差 10 分钟就为无效请求。目前格式为 yyyy-HH-dd HH:mm:ss，以后为时间戳格式 |
| signatureNonce | string   | 是       |                                                              |
| signature      | string   | 是       |                                                              |
| parameters     | string   | 是       |                                                              |
| user           | string   | 是       |                                                              |
| usertype       | string   | 否       |                                                              |

