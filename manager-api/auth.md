---
description: 测评权限设置管理
---

# 测评权限API

{% api-method method="get" host=" " path="/api/backdoor/permit/get" %}
{% api-method-summary %}
获取某个App Name的测评权限
{% endapi-method-summary %}

{% api-method-description %}
拿到该app name全部权限。
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

{% api-method-parameter name="manager\_sign" type="string" required=true %}
管理者API的sign
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



{% api-method method="post" host=" " path="/api/backdoor/permit/set" %}
{% api-method-summary %}
设置某个App Name的测评权限
{% endapi-method-summary %}

{% api-method-description %}
设置该app name全部权限。
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

{% api-method-parameter name="manager\_sign" type="string" required=true %}
管理者API的sign
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="auths" type="array" required=true %}
要设置的权限组成的数组
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

