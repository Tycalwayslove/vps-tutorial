---
title: MEU 员工使用说明
status: 待发放个人订阅
updated: 2026-10-09
tags: [MEU, 员工手册, 订阅]
---

# MEU 员工使用说明

这份说明适合第一次使用的同事。**先向公司负责网络服务的管理员领取写有你姓名的 MEU 个人订阅链接**，再按自己的设备安装软件。管理员会通过公司指定的私密渠道发放链接和离线安装包；目前尚未分配员工账号，发放时间待定。只安装软件、没有领取链接，还不能连接。你不需要登录 3x-ui 管理面板，也不需要服务器账号或密码。不知道管理员是谁时，请先问公司的 IT 对接人。

管理员计划为每人单独开通每月 **100 GiB** 流量，个人所有设备和节点合计使用，按月重置。个人账号尚未分配，因此本手册没有可直接使用的订阅链接。领到链接后，请只在自己的设备上使用，不要转发；链接本身就相当于访问凭据。

## 先看这一张表

管理员发给你的**订阅链接**会标明“**原始订阅**”“**Mihomo 订阅**”或“**旧版 Clash 订阅**”。它们对应同一个人，但格式不同。请按表格第二列选管理员发来的订阅链接；第三列的下载链接只用于获取软件，不能填进订阅地址栏。

| 你的设备和软件 | 建议使用的订阅链接 | 去哪里拿软件 |
|---|---|---|
| Windows：v2rayN（首选） | **原始订阅** | 向管理员领取离线包中的 `v2rayN-windows-64-desktop.zip`；[官方原文件](https://github.com/2dust/v2rayN/releases/download/7.24.9/v2rayN-windows-64-desktop.zip) |
| Windows：Clash Verge Rev | **Mihomo 订阅** | 离线包中的 `Clash.Verge_2.5.2_x64-setup.exe`；[官方原文件](https://github.com/clash-verge-rev/clash-verge-rev/releases/download/v2.5.2/Clash.Verge_2.5.2_x64-setup.exe) |
| Mac：v2rayN | **原始订阅** | Apple 芯片选 `v2rayN-macos-arm64.dmg`，Intel 芯片选 `v2rayN-macos-64.dmg`；[官方下载页](https://github.com/2dust/v2rayN/releases/tag/7.24.9) |
| Mac：Clash Verge Rev | **Mihomo 订阅** | Apple 芯片选 `Clash.Verge_2.5.2_aarch64.dmg`，Intel 芯片选 `Clash.Verge_2.5.2_x64.dmg`；[官方下载页](https://github.com/clash-verge-rev/clash-verge-rev/releases/tag/v2.5.2) |
| Android：v2rayNG | **原始订阅** | 多数手机选 `v2rayNG_2.2.6_arm64-v8a.apk`；[官方原文件](https://github.com/2dust/v2rayNG/releases/download/2.2.6/v2rayNG_2.2.6_arm64-v8a.apk) |
| iPhone／iPad：Shadowrocket | **原始订阅** | 在 [App Store 的 Shadowrocket 页面](https://apps.apple.com/app/shadowrocket/id932747118) 安装；是否收费以你所在地区商店显示为准 |
| Linux：Clash Verge Rev | **Mihomo 订阅** | 请管理员按你的发行版和处理器提供安装包，或从[官方发布页](https://github.com/clash-verge-rev/clash-verge-rev/releases)下载；当前离线包没有 Linux 版本 |
| 已安装的旧版 Clash for Windows | **旧版 Clash 订阅** | 仅供继续使用旧软件的同事；新电脑建议安装 Clash Verge Rev |

如果打不开 GitHub，直接请管理员通过公司批准的渠道交付 **`客户端离线分发包`** 文件夹；其中保存了上表所列的 Windows、Mac 和 Android 安装文件。iPhone／iPad 要从 App Store 安装；Linux 安装包需单独联系管理员。不要从陌生网页搜索同名软件。Windows 的 `.zip` 要先完整解压再运行；Mac 的 `.dmg` 双击打开后按提示安装；Android 的 `.apk` 只从管理员提供的文件或项目官方发布页获取。手机提示“禁止安装未知来源应用”时，确认文件确由管理员提供后，按系统提示给当前文件管理器一次安装权限；拿不准就联系管理员。

Mac 不知道自己是哪种芯片：点屏幕左上角苹果图标 → **关于本机**。写着“芯片 Apple …”就选 `arm64`／`aarch64`；写着“处理器 Intel …”就选 `64`／`x64`。普通 Windows 10／11 电脑选 `x64`；少数 Windows ARM 电脑请先问管理员。

## Windows 或 Mac：v2rayN

1. 安装并打开 v2rayN。Windows 完整解压后，进入解压出的文件夹并双击 `v2rayN.exe`；Mac 安装后从“应用程序”打开。若 Mac 阻止打开，先确认文件由管理员提供，再在“系统设置 → 隐私与安全性”按系统提示允许；不确定时联系管理员。
2. 点上方 **订阅分组 → 订阅分组设置**，新增一个分组，别名可写 `MEU-我的账号`。
3. 把管理员给你的 **原始订阅**完整粘贴到“可选地址 (Url)”，保存。
4. 回到主窗口，点 **订阅分组 → 更新订阅**。只保存分组不会自动下载节点。
5. 打开新分组，选择一个节点作为当前节点，再开启软件的系统代理。首次使用可先选标有“网页通用”或“受限网络”的节点。

按目前的开通方案，个人 100 GiB 订阅预计出现 **7 条节点**；实际数量以管理员发放时告知的为准，数量不符请联系管理员。软件界面中的“延迟”是连接快慢的参考值，**不是下载速度**。若看到节点但网页仍打不开，先检查是否已经选中节点并开启系统代理。

## Windows 或 Mac：Clash Verge Rev

1. 安装并打开 Clash Verge Rev，进入左侧 **订阅**页面。
2. 粘贴管理员给你的 **Mihomo 订阅**地址，点击导入；随后点击该订阅的 **使用**。
3. 进入 **代理**页面选一个节点；再到设置中打开 **系统代理**。普通办公网页先用系统代理即可。
4. 需要更新节点时，在“订阅”页点刷新。不要把“原始订阅”放进这个软件；它需要的是 YAML 格式的 Mihomo 订阅。

按目前方案，个人 100 GiB 组预计显示 **7 条节点**。如果软件提示“仅支持 YAML”或“配置不含 proxies”，通常是选错了订阅类型，请换成管理员发的 **Mihomo 订阅**地址。[Clash Verge Rev 官方订阅说明](https://www.clashverge.dev/guide/profile.html)

## Android：v2rayNG

1. 安装 v2rayNG 并打开。首次启动若系统询问网络或 VPN 权限，按系统提示处理。
2. 打开侧边菜单中的 **订阅分组设置**，新增订阅；备注填 `MEU-我的账号`，地址填管理员给你的 **原始订阅**。
3. 保存后执行 **更新订阅**，回到节点列表，选择一个节点，再点连接按钮。
4. 等待手机顶部出现 VPN 标志，再打开浏览器检查网页。

按目前方案预计看到 **7 条节点**。按钮名称可能随软件版本略有变化；关键是“新增订阅 → 更新订阅 → 选择节点 → 连接”，不要把整条 HTTPS 订阅地址当作单个节点导入。

## iPhone／iPad：Shadowrocket

1. 从上表的 App Store 页面安装 Shadowrocket。
2. 在应用里新增**订阅／Subscribe**，粘贴管理员给你的 **原始订阅**地址并保存。
3. 更新该订阅；等节点列表出现后选择一个节点，打开连接开关。
4. iOS 第一次弹出 VPN 配置许可时按系统提示允许；顶部出现 VPN 标志后再测试网页。

个人 100 GiB 组按目前方案预计有 **7 条节点**。Shadowrocket 的实际界面可能随版本变化；如果保存后列表还是空的，先找“更新订阅”，不要直接判断线路已坏。如果 App Store 无法安装，请联系管理员确认商店地区和可用客户端。本组尚未在公司员工的 iPhone 上逐条实测，遇到某条节点无法识别时先换另一条并联系管理员。

## 旧版 Clash for Windows 与鸿蒙手机

已经在用旧版 Clash for Windows 的同事，填 **旧版 Clash 订阅**。MEU 的这份兼容订阅只显示 **2 条节点**，这是旧软件不支持新协议造成的，**不表示 100 GiB 额度少了，也不表示其他节点故障**。建议以后换用 Clash Verge Rev，使用完整的 Mihomo 订阅。

仍能安装 Android 应用的鸿蒙手机可先尝试 v2rayNG 的 Android 安装包及**原始订阅**。纯鸿蒙环境不保证能运行 APK；当前离线包也没有经过验证的原生鸿蒙客户端。此类设备请先联系管理员，不要安装来历不明的“兼容版”。

## 三分钟排查

| 遇到的情况 | 先做什么 |
|---|---|
| 新建订阅后没有节点 | 先点“更新订阅”，再检查是否复制了完整的 HTTPS 地址；仍为空时，把软件版本和更新时报的错误发给管理员。 |
| Clash Verge Rev 提示格式不对 | 检查是否误用了“原始订阅”，应改用 **Mihomo 订阅**。 |
| 只有两条节点 | 你可能用的是旧版 Clash；这属于兼容版的正常结果。 |
| 有节点但网页打不开 | 确认已选中节点并打开连接／系统代理；再试另一条节点。 |
| 软件无法安装 | 核对 Windows／Mac 芯片类型或 Android APK 架构；必要时向管理员要对应安装包。 |
| 提示证书、订阅过期、流量用尽 | 暂停反复重试；不要关闭证书校验，保留错误截图并发给管理员核查。 |

向管理员求助时，发**设备系统、软件名称和版本、错误截图、是否已经更新订阅**即可。截图前遮住订阅 URL、二维码、节点密码和个人信息；不要把完整订阅链接贴到群里。

## 额度与账号

个人套餐计划为每人 **100 GiB／月**，每月 1 日重置。该额度是这个人所有设备、所有节点**合计**可用的流量，不是每台设备各有 100 GiB。管理员尚未发放员工账号；拿到个人订阅前，本手册只是安装与导入指南。日后换手机，可以在自己的新设备重新导入个人链接；离职、链接外泄或不再使用时请通知管理员停用或更换链接。

---

软件与格式来源：[v2rayN 官方订阅说明](https://github.com/2dust/v2rayN/wiki/Description-of-subscription)、[3x-ui v3.8.5 订阅说明](https://github.com/MHSanaei/3x-ui/blob/v3.8.5/docs/content/docs/en/config/subscription.mdx)、[Clash Verge Rev 官方使用指南](https://www.clashverge.dev/guide/profile.html)、[Shadowrocket App Store](https://apps.apple.com/app/shadowrocket/id932747118)。离线包版本与来源记录见管理员保存的 `客户端离线分发包/来源与版本.json`。
