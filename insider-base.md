---
description: Insider BaseController
---

# Insider模块基类

## 基本使用

该模块的命名空间为Insider\Base：

```php
<?php

namespace Insider;

use Insider\Base\BaseController;

class xxxController extends BaseController {
    
    ...
}
```

{% hint style="warning" %}
只要是需要用到inside相关的管理功能建议继承，可以减少开发的工作量。
{% endhint %}

## 基础属性

**insiderId :** inside接入者的唯一id，兼容旧版id，新版id从10000开始计数,id=1是超级管理员。

```php
$this->insiderId;
```

**APPNAME :** inside接入使用的app\_name。

```php
$this->APPNAME;
```

**APPKEY :** inside接入使用的app\_key。

```php
$this->APPKEY;
```

**iconfig :**  用于快速使用的`InsideConfig`对象，具体使用请看`InsideConfig`

```php
$this->iconfig;
```



## 基本函数

**检查是否有该API的权限`apiCan()`**

```php
$this->apiCan('excellent.base.test');   //检查是否支持优才版的做题接口
$this->apiCan('excellent.base');        //检查是否支持优才版的基础功能
$this->apiCan('excellent');             //检查是否支持优才版
```

**检查是否没有该API的权限`apiCannot()`**

```php
$this->apiCannot('excellent.base.test');   //检查是否不支持优才版的做题接口
$this->apiCannot('excellent.base');        //检查是否不支持优才版的基础功能
$this->apiCannot('excellent');             //检查是否不支持优才版
```

**链接拼装生成器`urlMaker()`**

```php
$url = 'http://t12.renaren.com/v2/profession/do';
$parameters = [
    'param1'=>'data1',
    'param2'=>'data2',
];
$fullUrl = $this->urlMaker($url,'get',$parameters,'html')['url'];

echo $fullUrl;
```

