---
description: Inside2.0后台使用说明
---

# 概况

## 系统结构

本项目基于[`Laravel 6.0`](https://laravel.com/docs/6.x/releases)和 [`laravel-admin`](https://laravel-admin.org/docs/zh/)，拥有他们的所有特性并加以扩展，下面为`app`目录的结构：

```bash
app
├── Admin
│   ├── Controllers
│   │   ├── Error
│   │   ├── Manager   //管理员功能模块
│   │   ├── HomeController.php  //首页入口
│   │   └── NewsController.php  //公告管理
│   └── routes.php
├── Insider   //接入者管理模块
│   ├── Base
│   │   ├── Barrier.php           //基础类的interface，用于实现不同账号之间的数据隔离
│   │   ├── BaseController.php    //基础类
│   │   ├── InsideConfig.php      
│   │   └── T12UserController.php 
│   ├── ApiDebuggerController.php //调试工具
│   ├── CallbackController.php    //回调查询
│   ├── Dashboard.php             //inside用户首页快捷类
│   ├── DocumentsController.php   //API文档
│   ├── QueriesController.php     //数据查询
│   └── StatisticsController.php  //数据统计（待开发）
├── Models
│   ├── Base
│   │   ├── Administrator.php  //覆盖默认Laravel-Admin类，用于扩展功能
│   │   ├── T12ApiAuth.php     //Inside接口权限授权
│   │   ├── T12App.php         //Inside2.0的全新接入者Inside App数据
│   │   └── T12User.php        //Inside 个人用户
│   ├── Information // 测评数据配置（例如：剩余查看权数量、回调链接、订制皮肤...）
│   │   └── TestInfo.php
│   ├── Logs  //日志
│   │   └── ApiErrorLogs.php
│   ├── News  //公告
│   │   └── InsideNews.php
│   ├── Old   //Inside1.0相关
│   │   ├── OldT12App.php //Inside1.0的接入者Inside App数据
│   │   └── RarAccount.php //Inside1.0的接入者账号数据
│   ├── Traits
│   │   └── CodeUser.php //用于快速关联T12User类的Traits
│   ├── Excellent
│   ├── Profession
│   ├── Special
│   └── ...
├── Facades
│   └── InsideConfig.php //获取inside专属config的快捷类
└── Helpers
    └── fun.common.php   //Inside使用的公共方法
```

{% hint style="info" %}
 以上仅为逻辑代码部分结构，还有config和resource两个文件夹是包含Inside代码的。
{% endhint %}

`config`目录结构如下:

```bash
config
└── Inside    //inside所有相关配置均放在此
    ├── ApiData  //用于存放API接口的内容，包括基础url、参数、备注、
    │   ├── excellent.php
    │   ├── profession.php
    │   ├── special.php
    │   ├── user.php
    │   └── ...
    ├── apiauth.php    //接口权限结构
    ├── apidebug.php   //api调试接口入口
    ├── queries.php    //只需配置，实现查询功能
    └── t12.php        //T12配置，坤哥用的，不知道啥功能
```



