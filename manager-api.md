---
description: 一套用于与企业后台4.0进行沟通的api接口
---

# 管理员API

{% api-method method="get" host=" " path="/api/backdoor/viewright/get" %}
{% api-method-summary %}
查询查看权数量
{% endapi-method-summary %}

{% api-method-description %}
查询测评码数量，查看权数量，可指定某一版本进行查询，也可以进行多版本查看
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="manager\_name" type="string" required=true %}
管理api专属的name
{% endapi-method-parameter %}

{% api-method-parameter name="app\_name" type="string" required=true %}
需要查询的企业的app name
{% endapi-method-parameter %}

{% api-method-parameter name="time\_stamp" type="number" required=true %}
时间戳.自从 Unix 纪元（格林威治时间 1970 年 1 月 1 日 00:00:00）到当前时间的秒数
{% endapi-method-parameter %}

{% api-method-parameter name="prefix" type="string" required=false %}
测评版本的英文简称
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
{
    "code": 1,
    "msg": "success",
    "data": [
        {
            "type": "mbti1",
            "remain_code": 98,
            "remain_report": 99
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="post" host=" " path="/api/backdoor/viewright/set" %}
{% api-method-summary %}
设置查看权剩余数量
{% endapi-method-summary %}

{% api-method-description %}
设置测评码创建数量、报告查看权数量。
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="manager\_name" type="string" required=true %}
管理api专属的name
{% endapi-method-parameter %}

{% api-method-parameter name="app\_name" type="string" required=true %}
需要查询的企业的app name
{% endapi-method-parameter %}

{% api-method-parameter name="time\_stamp" type="number" required=true %}
时间戳.自从 Unix 纪元（格林威治时间 1970 年 1 月 1 日 00:00:00）到当前时间的秒数
{% endapi-method-parameter %}

{% api-method-parameter name="prefix" type="string" required=true %}
测评版本的英文简称
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="code\_number" type="string" required=false %}
设置测评码剩余数量
{% endapi-method-parameter %}

{% api-method-parameter name="report\_number" type="string" required=false %}
设置报告查看权剩余数量
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



{% api-method method="get" host=" " path="/api/backdoor/callback/get" %}
{% api-method-summary %}
查询回调地址信息
{% endapi-method-summary %}

{% api-method-description %}
查询回调地址信息，可指定某一版本进行查询，也可以进行多版本查看
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="manager\_name" type="string" required=true %}
管理api专属的name
{% endapi-method-parameter %}

{% api-method-parameter name="app\_name" type="string" required=true %}
需要查询的企业的app name
{% endapi-method-parameter %}

{% api-method-parameter name="time\_stamp" type="number" required=true %}
时间戳.自从 Unix 纪元（格林威治时间 1970 年 1 月 1 日 00:00:00）到当前时间的秒数
{% endapi-method-parameter %}

{% api-method-parameter name="prefix" type="string" required=false %}
测评版本的英文简称
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
{
    "code": 1,
    "msg": "success",
    "data": [
        {
            "type": "leaderpro",
            "notify_url": "http://www.i.com/api/notify/receive"
        },
        {
            "type": "rp7",
            "notify_url": null
        },
        {
            "type": "motive",
            "notify_url": "http://www.i.com/api/notify/receive"
        },
        {
            "type": "mbti1",
            "notify_url": null
        },
        {
            "type": "ba",
            "notify_url": "http://www.i.com/api/notify/receive"
        },
        {
            "type": "glp1",
            "notify_url": null
        },
        {
            "type": "value2",
            "notify_url": null
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="post" host=" " path="/api/backdoor/callback/set" %}
{% api-method-summary %}
设置回调地址
{% endapi-method-summary %}

{% api-method-description %}
设置回调地址。
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="manager\_name" type="string" required=true %}
管理api专属的name
{% endapi-method-parameter %}

{% api-method-parameter name="app\_name" type="string" required=true %}
需要查询的企业的app name
{% endapi-method-parameter %}

{% api-method-parameter name="time\_stamp" type="number" required=true %}
时间戳.自从 Unix 纪元（格林威治时间 1970 年 1 月 1 日 00:00:00）到当前时间的秒数
{% endapi-method-parameter %}

{% api-method-parameter name="prefix" type="string" required=true %}
测评版本的英文简称
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="code\_number" type="string" required=false %}
设置测评码剩余数量
{% endapi-method-parameter %}

{% api-method-parameter name="report\_number" type="string" required=false %}
设置报告查看权剩余数量
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

