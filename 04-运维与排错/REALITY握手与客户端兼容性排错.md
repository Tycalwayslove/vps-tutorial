# REALITY 握手与客户端兼容性排错

这是本次确实发生的故障，不是虚构例题。最终可用配置见 [[VLESS-REALITY配置]]。

## 观察 → 检查 → 结果

| 顺序 | 动作 | 实际发现 |
| --- | --- | --- |
| 1 | 用 sing-box 1.12.22 连接初始 REALITY | `reality verification failed` |
| 2 | 检查服务端监听 | TCP 443 正在监听 |
| 3 | 用私钥推导公钥，比较 DB 与二维码 | 配对一致；Short ID、SNI 也一致 |
| 4 | VPS 用 OpenSSL 连接 Microsoft | TLS 1.3、X25519、h2、证书验证均通过 |
| 5 | 换官方 Xray 26.7.28 客户端 | 仍失败，重试最终 EOF |
| 6 | 在浏览器重启 Xray | 故障仍在，排除简单重启即可解决的情况 |
| 7 | 临时打开 REALITY“显示”诊断 | 核心提示默认最低版本 26.3.27，并提示不建议本次 Microsoft 目标 |
| 8 | 预检 Apple，再只改目标与 SNI | Xray 26.7.28 的 HTTPS 请求成功 |
| 9 | 关闭调试、重新导出二维码，再测 | 正确 UUID 成功，错误 UUID 失败 |

改动始终在浏览器入站编辑页完成。没有降低最低版本，也没有重新生成密钥来碰运气。最终目标为 `www.apple.com:443`、SNI 为 `www.apple.com`。

## 能得出的结论

OpenSSL 的普通 TLS 检查是必要的诊断信息，但不足以覆盖 REALITY 的全部握手行为。更换目标解决了本次当前 Xray 的失败；未捕获足够证据确定 Microsoft 目标失败的底层原因，因此不把它推广成“Microsoft 永远不能用”。

旧 sing-box 的失败还受到当前默认最低客户端版本约束。把新核心和旧核心的日志放在一起看，才能避免把所有故障归因于单一因素。

VMess 也出现过内核差异：同一导出链接，sing-box 1.12.22 失败而 Xray 26.7.28 通过。这份记录证明所测组合有差异，不证明所有 sing-box 版本都不支持 VMess。

## 下次遇到同类问题

依次核对 IP 和端口、核心是否运行、客户端版本、配对凭据、SNI/Short ID、目标的 TLS 条件，然后改一个变量做对照。调试结束关闭多余日志，重新导出修改后的节点。

来源：[REALITY 参数及默认最低版本](https://xtls.github.io/config/transports/reality.html)、[Xray v26.7.28](https://github.com/XTLS/Xray-core/releases/tag/v26.7.28)。
