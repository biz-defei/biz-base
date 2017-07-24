# 约定

服务的上报与下发，采用AES算法进行加密通讯。

各模块之间，服务通讯通过服务下发的ak与sk，参与参数md5签名\(规则参看[签名规则](/ying-yong-fa-xian-yu-zhu-ce-zhong-xin/qian-ming-gui-ze.md)\)，以作身份校验，访中间人攻击。

