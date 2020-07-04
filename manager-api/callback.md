---
description: 回调地址管理
---

# 回调地址API

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
{% api-method-parameter name="manager\_sign" type="string" required=true %}
calculate\_manager\_sign\(\)函数加密串
{% endapi-method-parameter %}

{% api-method-parameter name="manager\_name" type="string" required=true %}
manager专属id
{% endapi-method-parameter %}

{% api-method-parameter name="company\_id" type="number" required=true %}
企业id
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
    "code": 0,
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
{% api-method-parameter name="manager\_sign" type="string" required=true %}
calculate\_manager\_sign\(\)函数加密串
{% endapi-method-parameter %}

{% api-method-parameter name="manager\_name" type="string" required=true %}
manager专属id
{% endapi-method-parameter %}

{% api-method-parameter name="company\_id" type="number" required=true %}
企业id
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

