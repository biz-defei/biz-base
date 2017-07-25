# 获取用户菜单及权限

## 请求数据模型

```
{
    "unionId": "402847955d65df07015d65dfbebf0001",
    "modulType": "ProductCenter"
}
```

字段说明

| 字段 | 数据类型 | 描述 | 示例 |
| :--- | :--- | :--- | :--- |
| unionId | String | 统一用户id | 402847955d65df07015d65dfbebf0001 |
| modulType | String | 服务模块类型标识 | ProductCenter |

## 

## 返回数据模型

```
{
    "menus": [
        {
            "name": "商品中心",
            "icon": "fa fa-list",
            "children": [
                {
                    "name": "商品基础数据",
                    "icon": "fa fa-list",
                    "children": [
                        {
                            "name": "商品管理",
                            "url": "/products.do",
                            "icon": "fa fa-list",
                            "children": []
                        },
                        {
                            "name": "品牌管理",
                            "url": "/brands.do",
                            "icon": "fa fa-list",
                            "children": []
                        }
                    ]
                },
                {
                    "name": "商品池",
                    "icon": "fa fa-list",
                    "children": [
                        {
                            "name": "省公司商品管理",
                            "url": "/companyProducts.do",
                            "icon": "fa fa-list",
                            "children": []
                        }
                    ]
                }
            ]
        }
    ],
    "grantedAuthorities": [
        {
            "authority": "ROLE_PRODUCT"
        },
        {
            "authority": "OPT_PRODUCT_EDIT"
        }
    ]
}
```

字段说明

| 字段 | 数据类型 | 描述 | 示例 |
| :--- | :--- | :--- | :--- |
| menus | JsonArray | 菜单列表 | 如上的Jso，成员参看menu字段说明 |
| grantedAuthorities | JsonArray | 用户拥在的权限列表 | 参看GrantedAuthority字段说明 |

menu字段说明

| 字段 | 数据类型 | 描述 | 示例 |
| :--- | :--- | :--- | :--- |
| name | String | 名称 | 商品中心 |
| icon | String | 图标 | fa fa-list |
| url | String | 点击跳转链接 | /products.do |
| children | JsonArray | 子菜单 | Array中内容参看本身 |

GrantedAuthority字段说明

| 字段 | 数据类型 | 描述 | 示例 |
| :--- | :--- | :--- | :--- |
| authority | String | 权鉴字符串 | ROLE\_PRODUCT,OPT\_PRODUCT\_EDIT |



