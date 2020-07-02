---
description: T12用户数管理API
---

# 用户数API

{% api-method method="get" host=" " path="/api/backdoor/useright/get" %}
{% api-method-summary %}
查询用户数量
{% endapi-method-summary %}

{% api-method-description %}
查询正式用户剩余可用量，还有测试用户剩余可用量
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="manager\_name" type="string" required=true %}
manager专属id
{% endapi-method-parameter %}

{% api-method-parameter name="app\_name" type="string" required=true %}
需要查询的企业的app name
{% endapi-method-parameter %}

{% api-method-parameter name="time\_stamp" type="number" required=true %}
时间戳，自从 Unix 纪元\(格林威治时间 1970 年 1 月 1 日 00:00:00\)到当前时间的秒数。
{% endapi-method-parameter %}

{% api-method-parameter name="manager\_sign" type="string" required=true %}
calculate\_manager\_sign\(\)函数加密串
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "code": 1,
    "msg": "success",
    "data": {
        "remain_user": 481,
        "remain_test_user": 20
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host=" " path="/api/backdoor/useright/set" %}
{% api-method-summary %}
设置用户数量
{% endapi-method-summary %}

{% api-method-description %}
设置正式用户和测试用户的剩余可用量
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="manager\_name" type="string" required=true %}
manager专属id
{% endapi-method-parameter %}

{% api-method-parameter name="app\_name" type="string" required=true %}
需要查询的企业的app name
{% endapi-method-parameter %}

{% api-method-parameter name="time\_stamp" type="number" required=true %}
时间戳，自从 Unix 纪元\(格林威治时间 1970 年 1 月 1 日 00:00:00\)到当前时间的秒数。
{% endapi-method-parameter %}

{% api-method-parameter name="manager\_sign" type="string" required=true %}
calculate\_manager\_sign\(\)函数加密串
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="user\_num" type="number" required=false %}
正式用户数量
{% endapi-method-parameter %}

{% api-method-parameter name="tester\_num" type="number" required=false %}
测试用户数量
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



