# 注册协议

注册请求数据模型

```
{
    "modulType": "User_Center",
    "host": "https://cas.biz-united.com.cn",
    "description": "用户中心",
    "menuItems": [
        {
            "uniqueId": "M_UserList",
            "defaultName": "用户列表",
            "defaultDescription": "提供全部用户分页展示，搜索功能",
            "link": "/users.do",
            "authorizations": "ROLE_USER;OPT_USER_LIST",
            "icon": "fa fa-list",
            "resources": [
                {
                    "uniqueId": "R_UserAdd",
                    "defaultName": "添加",
                    "defaultDescription": "有添加用户的权限",
                    "authorizations": "ROLE_USER;OPT_USER_ADD"
                },
                {
                    "uniqueId": "R_UserDelete",
                    "defaultName": "删除",
                    "defaultDescription": "有删除用户的权限",
                    "authorizations": "ROLE_USER;OPT_USER_DELETE"
                }
            ]
        }
    ]
}
```

主体字段解析:

| 字段 | 数据类型 | 描述 | 示例 |
| :--- | :--- | :--- | :--- |
| modulType | String | 服务模块类型标识 | User\_Center |
| host | String | 模块访问地址 | [https://cas.biz-united.com.cn](https://cas.biz-united.com.cn) |
| description | String | 模块描述 | 用户中心，管理用户账号密码等基础信息 |



MenuItem字段解析

| 字段 | 数据类型 | 描述 | 示例 |
| :--- | :--- | :--- | :--- |
| uniqueId | String | 菜单唯一标识符 | M\_UserList |
| defaultName | String | 默认名字，仅第一次上报的时候，这个uniqueId名字为空的时候使用 | 用户列表 |
| defaultDescription | String | 默认描述，仅第一次上报的时候，这个uniqueId描述为空的时候使用 | 提供全部用户分页展示，搜索功能 |
| link | String | 跳转连接 | /users.do |
| authorizations | String | 这个链接本身需要的权限，多个权限用;号分割 | ROLE\_USER;OPT\_USER\_LIST |
| icon | String | 图标，符合ace标准 | fa fa-list |



Resource字段解析

| 字段 | 数据类型 | 描述 | 示例 |
| :--- | :--- | :--- | :--- |
| uniqueId | String | 资源唯一标识符 | R\_UserAdd |
| defaultName | String | 默认名字，仅第一次上报的时候，这个uniqueId名字为空的时候使用 | 添加 |
| defaultDescription | String | 默认描述，仅第一次上报的时候，这个uniqueId描述为空的时候使用 | 有添加用户的权限 |
| authorizations | String | 这个资源本身包含的权限，多个权限用;号分割 | ROLE\_USER;OPT\_USER\_ADD |



