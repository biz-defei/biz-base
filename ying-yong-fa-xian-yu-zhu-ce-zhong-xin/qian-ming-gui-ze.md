### 1、签名算法

签名生成的通用步骤如下：

第一步，设所有发送或者接收到的数据为集合M，将集合M内非空参数值的参数按照参数名ASCII码从小到大排序（字典序），使用URL键值对的格式（即key1=value1&key2=value2…）拼接成字符串stringA。

特别注意以下重要规则：

1. ◆ 参数名ASCII码从小到大排序（字典序）；
2. ◆ 如果参数的值为空不参与签名；
3. ◆ 参数名区分大小写；
4. ◆ 验证调用返回或微信主动通知签名时，传送的sign参数不参与签名，将生成的签名与该sign值作校验。
5. ◆ 微信接口可能增加字段，验证签名时必须支持增加的扩展字段

第二步，在stringA最后拼接上key得到stringSignTemp字符串，并对stringSignTemp进行MD5运算，再将得到的字符串所有字符转换为大写，得到sign值signValue。

◆ key设置路径：微信商户平台\(pay.weixin.qq.com\)--&gt;账户设置--&gt;API安全--&gt;密钥设置

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

> stringA="appid=wxd930ea5d5a258f4f&body=test&device\_info=1000&mch\_id=10000100&nonce\_str=ibuaiVcKdpRxkhJA"

第二步：拼接API密钥：

> stringSignTemp=stringA+"&key=192006250b4c09247ec02edce69f6a2d"//注：key为发起请求的modul的ak
>
> sign=MD5\(stringSignTemp\).toUpperCase\(\)="9A0A8659F005D6984697E2CA0A9CF3B7"//注：MD5签名方式
>
> sign=hash\_hmac\("sha256",stringSignTemp,key\)//注：HMAC-SHA256签名方式

最终得到最终发送的数据：

> appid=wxd930ea5d5a258f4f&mch\_id=10000100&device\_info=1000&body=test&nonce\_str=ibuaiVcKdpRxkhJA&sign=9A0A8659F005D6984697E2CA0A9CF3B7



