---
description: 专门用于管理Inside那堆config的类
---

# InsideConfig工具类

## 调用方式

**1.直接使用关键字new来创建**

```php
use Insider\Base\InsideConfig;

$object = new InsideConfig();
$data = $object->nameChoice('t12-excellent');
var_dump($data);
```

**2.用Laravel的Facades方式进行调用**

```php
use App\Facades\InsideConfig;

$data = InsideConfig::nameChoice('t12-excellent');
var_dump($data);
```

{% hint style="info" %}
具体有啥区别，可自行百度了解一下。
{% endhint %}

## Function介绍



### **list\(\)**

用于获取queries.php文件中的数据

_**参数：**_

| 类型 | 变量名 | 默认值 | 注释 |
| :--- | :--- | :--- | :--- |
| string | $type | 'all' | 分组key\(all,name,permisssion,code,notice,record,report\) |

_**返回值：**_

|  | 变量名 | 注释 |
| :--- | :--- | :--- |
| InsideConfig | $this |  |

_**例子：**_

```php
InsideConfig:list();        //获取整个文件的数据
InsideConfig:list('name');    //获取name数组
InsideConfig:list('code');    //获取model_code数组
```

