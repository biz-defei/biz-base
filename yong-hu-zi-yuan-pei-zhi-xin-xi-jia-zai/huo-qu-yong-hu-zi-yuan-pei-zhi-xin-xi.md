# 获取用户资源配置信息

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
    "data": {
        "key1": "value1",
        "key2": "{}",
        "key3": "[]"
    },
    "code": 200,
    "msg": ""
}
```

字段说明

| 字段 | 数据类型 | 描述 | 示例 |
| :--- | :--- | :--- | :--- |
| data | JsonObject | 配置信息的一个map | {"id":1} |



