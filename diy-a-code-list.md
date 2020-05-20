# 自定义一个测评码列表

## 实现过程

* 首先，找到`app\Insider\ReportList`文件夹，并新建一个`XxxReportList`类，必须实现`ListView`契约;

```php
<?php

namespace Insider\ReportList;


class XxxReportList implements ListView {
    
    public function listView($adminObject, array $reportType) {
        //实现报告列表的功能
        ...
    }
    
    
    public function filter(Grid &$grid) {
        //实现筛选功能
        ....
    }
}
```

* 接着，我们需要搞清楚这个XxxrReportList应该如何命名，因为这是自动加载的，所以命名不能太随意；

> _命名规则：_链接入口名字\(首字母大写\)+"ReportList"

* 例子：在**`t12_special_accessments`**表中的en\_name字段，例如MO动机意愿测评，英文名是motive，那么这个XxxList就应该叫做**`MotiveReportList.php`**
* 具体逻辑代码的实现，请依据[laravel-admin中的Grid实现](https://laravel-admin.org/docs/zh/model-grid)；
* 便捷实现方式：

```bash
php artisan Inside:Report motive
```



