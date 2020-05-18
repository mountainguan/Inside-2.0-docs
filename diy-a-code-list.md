# 自定义一个测评码列表

## 实现过程

* 首先，找到`Insider\QueriesController`，并插入一个`xxxList()`;

```php
public function xxxList() ($reportType) {
    ...
}
```

* 接着，我们需要搞清楚这个xxxList应该如何命名，因为这是自动加载的，所以命名不能太随意；

> _命名规则：_链接入口名字小写+"List"

* 例子：在**`t12_special_accessments`**表中的en\_name字段，例如MO动机意愿测评，英文名是motive，那么这个xxxList就应该叫做**`motiveList()`**
* 具体逻辑代码的实现，请依据[laravel-admin中的Grid实现](https://laravel-admin.org/docs/zh/model-grid)；

