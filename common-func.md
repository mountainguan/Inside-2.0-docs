# 公共方法

## create\_random\_code

创建测评码的字符串

_**参数：**_

| 类型 | 变量名 | 默认值 | 注释 |
| :--- | :--- | :--- | :--- |
| int | length |  | 需要生成的长度 |
| string | chars | 'ABCDEFGHIJKLMNPQRSTUVWXYZ0123456789' | 用于创建测评码的字符 |

_**返回值：**_

| 类型 | 注释 |
| :--- | :--- |
| string | 测评码 |

_**例子：**_

```php
$perfix = 'COLD';
$baseCode = create_random_code(8);    //获取8位数测评码
$code = $perfix.$baseCode;            //获取12位数测评码
echo $code;
```



## calculate\_app\_sign

生成签名串，用作数据交互json接口（即开发者服务器与人啊人服务器通信使用的sign）

_**参数：**_

| 类型 | 变量名 | 默认值 | 注释 |
| :--- | :--- | :--- | :--- |
| string | app\_key |  | app key |
| array | data |  | url上所有变量 |

_**返回值：**_

| 类型 | 注释 |
| :--- | :--- |
| string | 签名串 |

_**例子：**_

```php
$appKey = 'abcdddlsajldj';
$data = array(
        'param1' => 'data1',
        'param2' => 'data2',
    );
$sign = calculate_app_sign($appKey,$data); //生成sign
echo $sign;
```





## calculate\_app\_token

生成token，做测评和看报告，这两个html页面的接口（即普通用户会接触到的app\_token）

_**参数：**_

| 类型 | 变量名 | 默认值 | 注释 |
| :--- | :--- | :--- | :--- |
| string | app\_key |  | app key |
| string | code |  | 测评码 |
| int | time\_stamp |  | UNIX时间戳 |

_**返回值：**_

| 类型 | 注释 |
| :--- | :--- |
| string | token串 |

_**例子：**_

```php
$appKey = 'abcdddlsajldj';
$code = 'COLD5D8EAW91';
$timeStamps = time();
$token= calculate_app_token($appKey,$code,$timeStamps); //生成token
echo $token;
```



## calculate\_manager\_sign

用于生成manager\_sign

_**参数：**_

| 类型 | 变量名 | 默认值 | 注释 |
| :--- | :--- | :--- | :--- |
| string | manager\_key |  | manager key |
| array | data |  | url上所有变量 |

_**返回值：**_

| 类型 | 注释 |
| :--- | :--- |
| string | token串 |

_**例子：**_

```php
$appKey = 'abcdddlsajldj';
$code = 'COLD5D8EAW91';
$timeStamps = time();
$token= calculate_app_token($appKey,$code,$timeStamps); //生成token
echo $token;
```

