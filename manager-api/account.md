---
description: 账号创建等管理操作
---

# 管理账号API

{% api-method method="get" host=" " path="/backdoor/company/search" %}
{% api-method-summary %}
查询账号信息
{% endapi-method-summary %}

{% api-method-description %}
根据用户账号的中文名或英文名进行查找。
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="manager\_name" type="string" required=true %}
manager专属id
{% endapi-method-parameter %}

{% api-method-parameter name="time\_stamp" type="number" required=true %}
时间戳.自从 Unix 纪元（格林威治时间 1970 年 1 月 1 日 00:00:00）到当前时间的秒数
{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
用户名称或账号名
{% endapi-method-parameter %}

{% api-method-parameter name="manager\_sign" type="string" required=true %}
calculate\_manager\_sign\(\)函数加密串
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
1成功将会拿到用户的所有信息
{% endapi-method-response-example-description %}

```javascript
{
    "code": 0,
    "msg": "success",
    "data": {
        "id": 2,
        "username": "qishan",
        "name": "东莞企山网**技开发有限公司",
        "avatar": "http://inside.t12.rar/uploads/images/rar-logo.png",
        "created_at": "2020-02-27 03:17:02",
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host=" " path="/backdoor/company/info" %}
{% api-method-summary %}
获取用户信息
{% endapi-method-summary %}

{% api-method-description %}
获取用户的app name, app key等信息
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="manager\_sign" type="string" required=true %}
calculate\_manager\_sign\(\)函数加密串
{% endapi-method-parameter %}

{% api-method-parameter name="manager\_name" type="string" required=true %}
manager专属id
{% endapi-method-parameter %}

{% api-method-parameter name="time\_stamp" type="number" required=true %}
时间戳.自从 Unix 纪元（格林威治时间 1970 年 1 月 1 日 00:00:00）到当前时间的秒数
{% endapi-method-parameter %}

{% api-method-parameter name="company\_id" type="number" required=false %}
\(二选一\)【优先】企业id
{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=false %}
\(二选一\)用户名称或账号
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host=" " path="/backdoor/company/create" %}
{% api-method-summary %}
创建 账号操作
{% endapi-method-summary %}

{% api-method-description %}
创建账号信息
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="time\_stamp" type="number" required=true %}
时间戳.自从 Unix 纪元（格林威治时间 1970 年 1 月 1 日 00:00:00）到当前时间的秒数
{% endapi-method-parameter %}

{% api-method-parameter name="manager\_name" type="string" required=true %}
manger专属id
{% endapi-method-parameter %}

{% api-method-parameter name="manager\_sign" type="string" required=true %}
calculate\_manager\_sign\(\)函数加密串
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="username" type="string" required=true %}
账号
{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}
密码
{% endapi-method-parameter %}

{% api-method-parameter name="company\_name" type="string" required=true %}
企业名称
{% endapi-method-parameter %}

{% api-method-parameter name="company\_short\_name" type="string" required=false %}
企业简称
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="post" host=" " path="/backdoor/company/update" %}
{% api-method-summary %}
修改 账号操作
{% endapi-method-summary %}

{% api-method-description %}
修改账号信息
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="manager\_name" type="string" required=true %}
manager专属id
{% endapi-method-parameter %}

{% api-method-parameter name="time\_stamp" type="number" required=true %}
时间戳.自从 Unix 纪元（格林威治时间 1970 年 1 月 1 日 00:00:00）到当前时间的秒数
{% endapi-method-parameter %}

{% api-method-parameter name="manager\_sign" type="string" required=true %}
calculate\_manager\_sign\(\)函数加密串
{% endapi-method-parameter %}

{% api-method-parameter name="company\_id" type="string" required=true %}
企业id
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="username" type="string" required=true %}
账号
{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}
密码
{% endapi-method-parameter %}

{% api-method-parameter name="company\_name" type="string" required=true %}
企业名称
{% endapi-method-parameter %}

{% api-method-parameter name="company\_short\_name" type="string" required=false %}
企业简称
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host=" " path="/backdoor/company/status" %}
{% api-method-summary %}
获取账号状态
{% endapi-method-summary %}

{% api-method-description %}
用于查询账号是否处于启用状态
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="manager\_sign" type="string" required=true %}
calculate\_manager\_sign\(\)函数加密串
{% endapi-method-parameter %}

{% api-method-parameter name="manager\_name" type="string" required=true %}
manager专属id
{% endapi-method-parameter %}

{% api-method-parameter name="app\_name" type="string" required=true %}
需要查询的账号的app name
{% endapi-method-parameter %}

{% api-method-parameter name="time\_stamp" type="number" required=true %}
时间戳.自从 Unix 纪元（格林威治时间 1970 年 1 月 1 日 00:00:00）到当前时间的秒数
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "code": 0,
    "msg": "success",
    "data": {
        "status": "activated"
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host=" " path="/backdoor/company/lock" %}
{% api-method-summary %}
锁定/启用 账号操作
{% endapi-method-summary %}

{% api-method-description %}
锁定或启用账号
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="manager\_name" type="string" required=true %}
manager专属id
{% endapi-method-parameter %}

{% api-method-parameter name="app\_name" type="string" required=true %}
需要查询的账号的app name
{% endapi-method-parameter %}

{% api-method-parameter name="manager\_sign" type="string" required=true %}
calculate\_manager\_sign\(\)函数加密串
{% endapi-method-parameter %}

{% api-method-parameter name="time\_stamp" type="number" required=true %}
时间戳.自从 Unix 纪元（格林威治时间 1970 年 1 月 1 日 00:00:00）到当前时间的秒数
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "code": 0,
    "msg": "success",
    "data": []
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

