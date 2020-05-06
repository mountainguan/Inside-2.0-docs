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

> 用于获取`config/Inside/queries`文件中的数据

_**参数：**_

| 类型 | 变量名 | 默认值 | 注释 |
| :--- | :--- | :--- | :--- |
| string | type | 'all' | 分组key\(all,name,permisssion,code,notice,record,report\) |

_**返回值：**_

| 类型 | 注释 |
| :--- | :--- |
| InsideConfig | 它本身 |

_**例子：**_

```php
InsideConfig:list()->data;        //获取整个文件的数据
InsideConfig:list('name')->data;    //获取name数组
InsideConfig:list('code')->data;    //获取model_code数组
```

### \*\*\*\*

### **verChoice\(\)**

> 用于和`list()`方法搭配使用，动态取得所需要得值。

_**参数：**_

| 类型 | 变量名 | 默认值 | 注释 |
| :--- | :--- | :--- | :--- |
| string | version |  | 链接里传进来得版本名，如t12-profession |

_**返回值：**_

| 类型 | 注释 |
| :--- | :--- |
| string | 被取出的目标数值 |

_**例子：**_

```php
InsideConfig:list('name')->verChoice('special');//获取专项测评的名称
```



### **nameChoice\(\)**

> 依据链接传入的版本名，直接获取所有与在`config/Inside/queries`中的相关数据

_**参数：**_

| 类型 | 变量名 | 默认值 | 注释 |
| :--- | :--- | :--- | :--- |
| string | version |  | 链接里传进来得版本名，如t12-profession |

_**返回值：**_

| 类型 | 注释 |
| :--- | :--- |
| InsideConfig | 它本身 |

_**例子：**_

```php
$object = InsideConfig:nameChoice('t12-profession');
$object->zh_name;    //链接传入的名字
$object->en_name;    //该版本的英文名兼版本权限名称
$object->report_type;//报告类型
$object->CODE_MODEL; //测评码模型
$object->NOTICE_MODEL;//回调通知模型
$object->RECORD_MODEL;//日志记录模型
```



### **auth\(\)**

> 获取`config/Inside/apiauth`文件上的某一版本的权限结构。

_**参数：**_

| 类型 | 变量名 | 默认值 | 注释 |
| :--- | :--- | :--- | :--- |
| string | type | 'all' | 版本名称 |

_**返回值：**_

| 类型 | 注释 |
| :--- | :--- |
| InsideConfig | 它本身 |

_**例子：**_

```php
InsideConfig::auth('excellent')->data;    //使用版本的权限名进行获取
```



### **debugger\(\)**

> 获取`config/Inside/apidebug`文件上的某一版本的调试接口信息。

_**参数：**_

| 类型 | 变量名 | 默认值 | 注释 |
| :--- | :--- | :--- | :--- |
| string | type | 'all' | 版本名称 |

_**返回值：**_

| 类型 | 注释 |
| :--- | :--- |
| InsideConfig | 它本身 |

_**例子：**_

```php
InsideConfig::debugger()->data;    //使用版本的权限名进行获取
```

