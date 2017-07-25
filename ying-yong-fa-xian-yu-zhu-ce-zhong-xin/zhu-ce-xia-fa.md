# 注册下发

注册下发数据模型

```
{
    "moduls": [
        {
            "modulType": "UserCenter",
            "host": "https://cas.biz-united.com.cn",
            "description": "用户中心",
            "ak": "AccessKey",
            "sk": "SecretKey",
            "customConfig": ""
        },
        {
            "modulType": "AuthorityCenter",
            "host": "https://authority.biz-united.com.cn",
            "description": "权限管理中心",
            "ak": "AccessKey",
            "sk": "SecretKey",
            "customConfig": ""
        }
    ],
    "code": 200,
    "msg": ""
}
```

主体字段解析

| 字段 | 数据类型 | 描述 | 示例 |
| :--- | :--- | :--- | :--- |
| moduls | JsonArray | 已经在服务中心注册的组件 | 参考Modul字段解析表 |

Modul字段解析

| 字段 | 数据类型 | 描述 | 示例 |
| :--- | :--- | :--- | :--- |
| modulType | String | 服务模块类型标识 | UserCenter |
| host | String | 模块访问地址 | [https://cas.biz-united.com.cn](https://cas.biz-united.com.cn) |
| description | String | 描述 | 用户中心 |
| ak | String | 公钥 | QSemJMtAw7eEeHjc |
| sk | String | 密钥 | 3TpsNwZVn4GQ5sC2W4W7M3covScC3bKs |
| customConfig | String | 自定义配置 | 任意字符串，推荐JsonString |
| code | Integer | 状态码 | 参看[通讯数据模型约定](/tong-xun-shu-ju-mo-xing-yue-ding.md)，或状态码说明表 |
| msg | String | 消息 | 签名不正确，授权未通过 |



