# ALPN

ALPN 是 Application-Layer Protocol Negotiation，即“应用层协议协商”。TLS 握手时，双方协商加密连接里准备使用哪种应用协议，可以类比电话接通前先确定“接下来讲哪种语言”。

| 常见值 | 含义 | 本次位置 |
| --- | --- | --- |
| `http/1.1` | HTTP/1.1 | 两个 WebSocket + TLS 入站 |
| `h2` | HTTP/2 | Trojan 保留的候选值；目标 TLS 检查也验证 h2 |
| `h3` | HTTP/3 | Hysteria2 的 QUIC 连接 |

ALPN 不是端口号，不是加密算法，也不应把所有选项都勾上。客户端、服务器与传输方式必须兼容。选择 h3 不会自动把普通 TCP 服务改造成 QUIC。

参见 [[WebSocket]]、[[QUIC]]、[[04-浏览器配置六种入口]]。

来源：[RFC 7301](https://www.rfc-editor.org/rfc/rfc7301)。
