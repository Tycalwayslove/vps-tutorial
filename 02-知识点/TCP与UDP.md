# TCP 与 UDP

网络数据会被拆成很多小块发送。TCP 与 UDP 是传递数据的两种基础方式。

TCP 负责建立连接、按顺序交付字节，并处理丢失重传。UDP 提供独立的数据报传送，本身不保证送达和顺序。使用 UDP 的上层程序可以自己实现可靠性和拥塞控制，例如基于 QUIC 的 Hysteria2。

因此“UDP 必然快”“TCP 必然慢”都不准确。真实结果取决于线路、丢包、算法和网络是否限制 UDP。

| 本次场景 | 关注什么 |
| --- | --- |
| VLESS＋TCP＋REALITY | TCP 端口是否能建立连接 |
| Hysteria2 | UDP 能否通过、QUIC/TLS 能否握手 |
| Shadowsocks TCP 与 UDP | 两种传送路径要分别验证 |

TCP 测试成功不能证明 UDP 成功。在端口检查工具里填相同的数字，也不代表测试了同一条传输路径。

继续阅读：[[协议传输与安全层]]。来源：[TCP RFC 9293](https://www.rfc-editor.org/rfc/rfc9293)、[UDP RFC 768](https://www.rfc-editor.org/rfc/rfc768)、[QUIC RFC 9000](https://www.rfc-editor.org/rfc/rfc9000)。
