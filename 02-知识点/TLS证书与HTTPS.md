# TLS 证书与 HTTPS

TLS 用于保护通信：协商加密、校验数据，并帮助客户端验证服务器身份。HTTPS 可以先理解为 HTTP 在 TLS 保护下传输。

证书包含服务器的公钥与被认证的名字或 IP，并由证书机构签名。私钥是服务器证明自己确实持有该身份的秘密。`fullchain.pem` 常保存证书链，`privkey.pem` 保存对应私钥；路径可以写进教程，私钥内容不能公开。

客户端校验一般要同时满足：证书链可信、证书未过期、访问身份与证书匹配。如果实际证书签给 `example.com`，直接用另一个名字访问可能失败。

从 2026 年起，Let’s Encrypt 已普遍提供 IP 地址证书。本次取得的是包含 tyccc IPv4 地址的短期证书，有效期约 160 小时。因此不必为了这次 TLS 实验临时购买域名，但必须做好 [[ACME与证书续期]]。

这也说明“TLS 一定需要域名”已经不准确。域名证书和 IP 证书都需要验证对应资源的控制权。

面板表单将证书文件路径标为“公钥”时，实际填写的是完整证书链文件路径；它不是让你粘贴 REALITY 的公钥。这两种配置不要互换。

来源：[Let’s Encrypt IP 证书正式可用公告](https://letsencrypt.org/2026/01/15/6day-and-ip-general-availability)、[Project X TLS 配置](https://xtls.github.io/config/transports/tls.html)。
