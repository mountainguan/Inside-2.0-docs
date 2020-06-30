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
$managerKey = 'abcdddlsajldj';
$data = array(
        'param1' => 'data1',
        'param2' => 'data2',
    );
$sign = calculate_manager_sign($managerKey,$data); //生成sign
echo $sign;
```

_**函数代码：**_

```php
/**
 * 生成签名串 manager_sign
 *
 * @param string $manager_keyapp_key,接入者密钥
 * @param string $time_stamp,时间戳.自从 Unix 纪元（格林威治时间 1970 年 1 月 1 日 00:00:00）到当前时间的秒数
 * @return  string // 生成签名串,只取前10位
 */

function calculate_manager_sign($manager_key, $data) {
    foreach ($data as $key => $value) {
        if (stristr($key, 'debug_') !== false)
            unset($data[$key]);
    }
    unset($data['manager_name'], $data['manager_sign']);
    $data['manager_key'] = $manager_key;  // manager_key
    ksort($data);                 // 所有变量按key字母从小到大排序
    $str = http_build_query($data); // 生成string字符，key1=value1&key2=value2&.....
    $str = substr(sha1($str), 0, 10);  // 生成签名串,只取前10位
    return $str;
}
```

