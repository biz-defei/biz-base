# 注册上报

注册请求数据模型

```
{
    "modulType": "User_Center",
    "host": "https://cas.biz-united.com.cn",
    "description": "用户中心",
    "ak": "AccessKey",
    "sk": "SecretKey",
    "customConfig": ""
}
```

主体字段解析:

| 字段 | 数据类型 | 描述 | 示例 |
| :--- | :--- | :--- | :--- |
| modulType | String | 服务模块类型标识 | User\_Center |
| host | String | 模块访问地址 | [https://cas.biz-united.com.cn](https://cas.biz-united.com.cn) |
| description | String | 模块描述 | 用户中心，管理用户账号密码等基础信息 |
| ak | String | 公钥 | 不为空的字符串 |
| sk | String | 密钥 | 长度为32位的字符串 |
| customConfig | String | 自定义配置 | 任意字符串，推荐JsonString |



