# WebSocket

WebSocket 是让客户端和服务器保持双向通信的一种方式。可以把普通 HTTP 请求想成“问一次、答一次”，WebSocket 则像接通后持续对话。本次把代理数据放进 WebSocket 连接里传输。

它是**传输方式**，不是 VLESS/VMess 的用户认证替代品，也不是 TLS 的加密替代品。VLESS + WS + TLS 里三层各有职责，见 [[协议传输与安全层]]。

本次路径 `/vless-ws` 和 `/vmess-ws` 用来区分处理入口。客户端的路径、服务端路径必须匹配；路径不必是一个能在文件管理器找到的真实文件夹。Host 字段也不是 IP 的同义词。

本次使用 HTTP/1.1 Upgrade，ALPN 只选 http/1.1。其他传输或协议版本不能照搬这个结论。示例见 [[VLESS-WebSocket-TLS配置]]。

来源：[MDN WebSocket](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API)、[Xray WebSocket](https://xtls.github.io/config/transports/websocket.html)。
