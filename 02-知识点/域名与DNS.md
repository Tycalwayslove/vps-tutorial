# 域名与 DNS

域名是方便人记忆的名字，例如 `example.com`。DNS 是把名字查询成地址等信息的系统。

域名和 VPS 是不同的资源。在服务器面板里把 Hostname 写成某个域名，不代表你已经注册这个域名，也不代表互联网已经知道它对应的 IP。

常见记录：`A` 指向 IPv4 地址，`AAAA` 指向 IPv6 地址，`CNAME` 指向另一个名字。TTL 表示解析结果可以缓存多久，所以改动后不一定马上在所有地方生效。

证书申请和客户端连接时，都要区分“填写的名字”和“实际连接的地址”。域名拼写、DNS 记录、证书身份不一致，可能导致解析或 TLS 校验失败。

REALITY 中的目标网站名字也不等于你的 VPS 地址。客户端仍然连接你的 VPS，目标名字参与 REALITY 的握手配置。

Cloudflare 的“仅 DNS”和“已代理”还会改变请求是否经过其边缘网络，见 [[CDN与DNS代理状态]]。有域名不自动隐藏源站 IP；是否经过代理、源站是否有其他公开记录，是另外的问题。

继续阅读：[[TLS证书与HTTPS]]、[[REALITY与Vision]]。来源：[Cloudflare DNS 学习中心](https://www.cloudflare.com/learning/dns/what-is-dns/)、[DNS 基础 RFC 1034](https://www.rfc-editor.org/rfc/rfc1034)。
