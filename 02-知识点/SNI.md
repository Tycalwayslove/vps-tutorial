# SNI

SNI 是 Server Name Indication，直译“服务器名称指示”。同一个服务器 IP 可以承载多个域名，客户端在 TLS 握手时用这个名字帮助服务器选择相应站点和证书。

**连接地址**回答“拨到哪里”，**验证名称**回答“预期对方是谁”。例如 REALITY 连接地址是 tyccc 的 IP，而本次 serverName/SNI 是 `www.apple.com`；两者不同是方案设计的一部分。

传统 TLS 入口使用 IP 证书时，客户端仍需验证证书的 IP SAN。IP 字面量通常不会作为 DNS host_name SNI 在线路上发送；软件界面把 serverName 也标作“SNI”容易造成混淆。本次字段填写真实 IP，不靠忽略证书错误解决不匹配。

参见 [[TLS证书与HTTPS]]、[[VLESS-REALITY配置]]。

来源：[RFC 6066 第 3 节](https://www.rfc-editor.org/rfc/rfc6066#section-3)、[Xray TLS](https://xtls.github.io/config/transports/tls.html)。
