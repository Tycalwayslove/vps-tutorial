---
title: 新 MEU 节点：从搬瓦工系统恢复到 3x-ui 部署
status: 已完成
tags: [VPS, 搬瓦工, 3x-ui, MEU, 迁移]
---

> [!important] 本次范围
> 这台新服务器用来替换已无法稳定访问的旧 MEU IP。它复用 tyccc 的**直连**协议组合和订阅设计；不迁移 ISP 链式出站，因为原静态住宅 IP 已失效。

## 1. 先确认“系统真的装好了”

搬瓦工面板里的 **Mount ISO（挂载镜像）** 和 **Install new OS（安装新系统）** 不是一回事。

- 挂载镜像只是把安装光盘放进虚拟光驱；原操作系统仍可能继续启动。
- 安装新系统才会把系统盘重装为选定的发行版，并准备好 SSH 服务。
- 本次检查时，服务器处于 `Running`，但面板显示 `SSH Port: Unavailable`，系统仍是 AlmaLinux 9，同时挂着 Debian 12 的安装镜像。这解释了为什么外部 SSH 端口不可用：它不是网络被墙，而是尚未完成可远程管理的系统安装。

推荐选择 **Debian 12 x86_64**。原因是 tyccc 已使用 Debian 12，软件包、服务名称和排障步骤都能保持一致。

安装完成后的最低验收标准：

1. 搬瓦工主控页面显示 `Operating system: Debian 12`。
2. 页面不再显示 `SSH Port: Unavailable`。
3. 本机可以用 `ssh root@新IP` 建立连接。
4. `systemctl is-active ssh` 返回 `active`。

关联概念：[[Linux与root]]、[[SSH与主机指纹]]、[[KVM与VPS选型]]。

## 2. 本次要部署的直连入站

以下清单来自 tyccc 当前可用的直连模板。端口沿用，是为了让两台机器的教程和排障术语一致；每台机器会重新生成 UUID、密码、REALITY 密钥和订阅令牌，不能复制旧机密钥。

| 用途名称 | 协议组合 | 端口 | 说明 |
|---|---|---:|---|
| 视频/低延迟优先 | Hysteria2 + TLS + UDP | 443 | 适合支持 QUIC/UDP 的客户端 |
| 受限网络 | VLESS + RAW + REALITY | 2443 | 直连 TCP，使用 REALITY 握手 |
| 网页通用 | Shadowsocks | 18388 | 兼容性较好 |
| 网页兼容 | VLESS + WebSocket + TLS | 18443 | 适用于需要 WebSocket 的客户端 |
| 兼容备用 | VMess + WebSocket + TLS | 18080 | 为旧客户端准备 |
| 网页兼容 | Trojan + TLS | 19443 | TLS 外形的备用入口 |
| 实验 | VLESS + XHTTP + REALITY | 2444 | 用于比较 XHTTP 和 RAW |
| 实验 | TUIC v5 + TLS + UDP | 4443 | 用于比较 QUIC 类传输 |

不创建的部分：所有标有“ISP出口”的入站、SOCKS 出站、路由规则和链式代理。它们需要可用的住宅静态 IP 才有意义。

协议原理见：[[VLESS-REALITY配置]]、[[Hysteria2配置]]、[[VLESS-WebSocket-TLS配置]]、[[VMess-WebSocket-TLS配置]]、[[Trojan-TLS配置]]、[[XHTTP与传输选择]]、[[QUIC]]。

## 3. 订阅与流量组

新面板保留两个用户组：

| 组 | 节点范围 | 流量规则 | 适合谁 |
|---|---|---|---|
| 全线路 | 上表所有直连节点 | 不限量 | 自用和完整测试 |
| 每月 100 GB | 除 TUIC 外的 7 条直连节点 | 每月自动重置为 100 GiB | 需要明确月度上限的用户 |

TUIC 在当前 3x-ui 版本中的用量限制按**整条入站**计算，不能像其他协议那样可靠地对单个订阅用户限额。因此月度组不分配 TUIC；全线路组仍可用它做协议实验。[3x-ui 客户端配置说明](https://github.com/MHSanaei/3x-ui/blob/main/docs/content/docs/en/config/clients.mdx)

ISP 出口恢复后，才另建“全线路含 ISP”和“直连专用”两类组，避免用户误以为现在的节点会从住宅 IP 出口。

## 4. 网络与安全基线

- 3x-ui 面板只监听本机；公网访问将通过 Cloudflare Tunnel 提供。
- 代理入站只放行本表所需 TCP/UDP 端口；SSH 仅供管理并启用限速规则。
- IP TLS 证书采用自动续期任务，并在证书到期前自动重载服务。
- 管理入口和订阅入口使用 `meumall.cc.cd` 的独立子域名。两个 DNS 记录都是指向 Cloudflare Tunnel 的代理 CNAME，本次不需要把 A 记录改成新 IP。

关联概念：[[防火墙与监听地址]]、[[ACME与证书续期]]、[[CDN与DNS代理状态]]、[[入站出站与路由]]。

## 5. 验收记录

- [x] 新实例已识别，且未误操作旧搬瓦工实例。
- [x] 已确认当前 SSH 不可用的根因是系统状态，而不是客户端配置。
- [x] 已核对 tyccc 的直连协议清单。
- [x] 通过“Install new OS”完成 Debian 12.14 安装，SSH 服务可用。
- [x] 通过 SSH 部署 3x-ui v3.8.5；面板与订阅服务仅监听 `127.0.0.1`，UFW 与 fail2ban 已启用。
- [x] 创建 8 条直连入站和两类订阅用户；全线路 8 条，每月 100 GiB 组 7 条。
- [x] 签发并验证新 IP 证书；设置每 6 小时检查一次的自动续期任务。
- [x] 将新机接入现有 `meu-panel-sub` Tunnel；把面板路由改为 `http://127.0.0.1:1573`，订阅路由改为 `http://127.0.0.1:2096`。
- [x] 旧机上的 `cloudflared` 服务已停止并禁止开机自启；Cloudflare 只显示新机 `144.34.129.104` 一条活跃连接。
- [x] 从本机用独立 Xray / sing-box 客户端逐条真实代理访问外网，8 条入站均成功，出口 IP 为新服务器 `144.34.129.104`。
- [x] 公网面板登录、两类订阅均已验收：全线路连续 8 次返回 8 条节点；每月 100 GiB 组连续 8 次返回 7 条节点。
- [ ] 在实际使用的 v2rayN / v2rayNG 上导入订阅，确认客户端能识别并测速。这个验收需要在对应客户端完成；服务端和公网订阅响应已验证。

## 6. 域名切换为什么要关掉旧连接

目前 Cloudflare DNS 中的 `panel`、`sub` 都代理到现有的 `meu-panel-sub` Tunnel，不存在需要改写的 A 记录。先让新机器作为第二个连接接入 Tunnel，再修改公开路由，能在新机准备好以前保留旧入口。但**同一个 Tunnel 有两个活跃连接时，Cloudflare 会把请求分配给两台机器**：我们实际观察到新订阅地址有时返回 200、有时返回 307，原因是旧机还在运行旧的订阅路径。

因此，路由修改后还需关闭旧机的 `cloudflared` 服务，并确认 Cloudflare 的 `Active replicas` 只剩 1，`Origin IP` 是新 IP。旧 MEU 的 IPv4 无法从本机建立 SSH 连接，但它的 IPv6 仍可连接；先用已有 SSH 记录核对主机指纹，再通过终端关闭旧 Tunnel。此操作只停旧机的 Tunnel 服务，不会删除旧机数据或关闭其他服务。

> [!NOTE] 管理入口与订阅入口
> 面板：`https://panel.meumall.cc.cd/login/`。两类完整订阅 URL、管理员账号和密码都保存在工作目录的 `account.md`，不放进 Git 教程。把订阅 URL 填到 v2rayN 的「订阅分组设置 → 可选地址 (Url)」，然后执行更新订阅；它不是单条节点的分享链接。

Cloudflare Tunnel 只代理面板与订阅的网页请求。客户端使用的 VLESS、Hysteria2 等节点仍直接连接新服务器 IP；隐藏面板地址的源站 IP，不等于隐藏这些代理节点的 IP。想让节点也显示域名，需要另行配置节点地址和相应 DNS，并不自动改变它们的公网暴露方式。

## 7. 之后怎么检查

1. 打开面板地址，应正常显示登录页；用 `account.md` 里的新账号登录。
2. 在 v2rayN 中新增订阅分组，填入对应的完整 URL，更新后分别应看到 8 条或 7 条节点。
3. Cloudflare Tunnel 页面应只显示新 IP 一条活跃连接。若又出现第二条旧 IP 连接，检查旧机的 `cloudflared` 是否被重新启动。
4. 遇到证书错误，先检查证书有效期、自动续期任务和 3x-ui 重载状态；不要在客户端关闭证书验证。

相关出处：[Cloudflare Tunnel 副本](https://developers.cloudflare.com/tunnel/configuration/)、[Cloudflare Tunnel 路由](https://developers.cloudflare.com/tunnel/concepts/routing/)、[Cloudflare Tunnel 运行状态](https://developers.cloudflare.com/tunnel/observability/)。

版本与原理出处：[3x-ui v3.8.5](https://github.com/MHSanaei/3x-ui/releases/tag/v3.8.5)、[3x-ui 订阅配置](https://github.com/MHSanaei/3x-ui/blob/main/docs/content/docs/en/config/subscription.mdx)、[Cloudflare Tunnel 路由](https://developers.cloudflare.com/tunnel/get-started/)、[Let's Encrypt IP 证书](https://letsencrypt.org/2026/01/15/6day-and-ip-general-availability/)。
