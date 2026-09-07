# REALITY 与 Vision

REALITY 是 Xray 的一种传输安全机制，本教程将它与 VLESS 和 TCP/RAW 组合。Vision 是对应的流控模式，常见取值为 `xtls-rprx-vision`。

理解字段时分清两类地址：客户端的“服务器地址”填写自己的 VPS；REALITY 的“目标”和 SNI 填写选定的 TLS 目标网站。本次最终选用 `www.apple.com:443`，先从 VPS 检查其 TLS 连接，再验证实际代理请求。初始 Microsoft 目标的失败记录见 [[REALITY握手与客户端兼容性排错]]。

REALITY 使用独立的密钥对：私钥留在服务器，客户端取得公钥等连接参数。这里公钥也是客户端认证材料，按秘密管理。目标网站不会因此变成你的代理服务器，也不是用来保管你的私钥。

Short ID 是握手配置的一部分，不是用户名；客户端要使用服务器接受的值。uTLS 指纹是客户端 TLS 握手特征的配置，面板默认例子为 `chrome`。

不要把 REALITY 理解成匿名保证，也不要把复制某组参数当作永远有效。目标可达性、核心版本和客户端兼容性都可能改变。本次保留默认最低客户端版本策略，优先使用相容的 Xray 客户端验证。

WebSocket 实验使用独立 TLS 配置，不套用 TCP REALITY 的 Vision flow。对应比较见 [[协议传输与安全层]]。

来源：[3x-ui REALITY 配置指南](https://docs.sanaei.dev/docs/config/reality/)、[Project X REALITY 字段说明](https://xtls.github.io/config/transports/reality.html)。
