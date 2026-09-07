# QUIC

QUIC 是构建在 UDP 上的传输协议，自己处理可靠传输、拥塞控制和加密等机制。好比快递外面用一种较简单的运输通道，里面仍有自己的编号、重传和签收规则。

“底层是 UDP”不等于“应用收到的数据任意丢失也不管”。但网络如果直接阻断 UDP，QUIC 仍无法工作。HTTP/3 使用 QUIC；本次 [[Hysteria2配置]] 也依赖它。

本次 Hysteria2 占 UDP 443，REALITY 占 TCP 443，可以同时运行。一个 HTTPS 代理测试成功，证明 Hysteria2 建立了工作中的连接；另做 UDP DNS 测试，是为了验证代理承载 UDP 应用数据的能力，两个验证对象不同。

来源：[RFC 9000](https://www.rfc-editor.org/rfc/rfc9000)、[Hysteria2 项目](https://v2.hysteria.network/)。
