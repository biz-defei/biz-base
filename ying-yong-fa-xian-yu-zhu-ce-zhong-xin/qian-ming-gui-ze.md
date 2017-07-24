### 1、签名算法

签名生成的通用步骤如下：

第一步，设所有发送或者接收到的数据为集合M，将集合M内非空参数值的参数按照参数名ASCII码从小到大排序（字典序），使用URL键值对的格式（即key1=value1&key2=value2…）拼接成字符串stringA。

特别注意以下重要规则：

1. ◆ 参数名ASCII码从小到大排序（字典序）；
2. ◆ 如果参数的值为空不参与签名；
3. ◆ 参数名区分大小写；
4. ◆ 验证调用返回或主动通知签名时，传送的sign参数不参与签名，将生成的签名与该sign值作校验。

第二步，在stringA最后拼接上sk得到stringSignTemp字符串，并对stringSignTemp进行MD5运算，再将得到的字符串所有字符转换为大写，得到sign值signValue。

◆ sk为被请求modul自行设置，通过sdk上报到服务发现中心，然后下发到各modul中

举例：

假设传送的参数如下：

> ak： d930ea5d5a258f4f
>
> id： 1000
>
> name： test
>
> nonce\_str： ibuaiVcKdpRxkhJA

第一步：对参数按照key=value的格式，并按照参数名ASCII字典序排序如下：

> stringA="ak=d930ea5d5a258f4f&id=1000&name=test&nonce\_str=ibuaiVcKdpRxkhJA" //注：ak为发起请求的modul的ak

第二步：假设你访问的modul的sk="192006250b4c09247ec02edce69f6a2d"，拼接API签名：

> stringSignTemp=stringA+"&sk=192006250b4c09247ec02edce69f6a2d"//注：sk为被请求的modul的sk
>
> sign=MD5\(stringSignTemp\).toUpperCase\(\)="69B0E43727B2C87A47957B6C2EB6D071"//注：MD5签名方式

最终得到最终发送的数据：

> ak=d930ea5d5a258f4f&id=1000&name=test&nonce\_str=ibuaiVcKdpRxkhJA&sign=69B0E43727B2C87A47957B6C2EB6D071

### 2、生成随机数算法

微信支付API接口协议中包含字段nonce\_str，主要保证签名不可预测。我们推荐生成随机数算法如下：调用随机数函数生成，将得到的值转换为字符串。

