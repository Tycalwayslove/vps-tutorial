# 公司网络与 AI 工具使用说明（MEU / tyccc）

这两条线路供同事在工作中访问所需的网站、资料和各类 AI 工具。请遵守公司规定及当地法律，保护账号和工作数据，不要把订阅地址发到公开群聊。

## 订阅链接（先选设备和软件，再复制对应类型）

**本仓库是公开的，因此下面是占位符。管理员分发的本地版会显示可直接复制的链接。** 先选线路，再按软件复制相应格式；这些是订阅地址，不是软件下载地址。

### MEU：工作优先

| 订阅类型 | 链接 | 适用软件 |
|---|---|---|
| 原始订阅 | `{{MEU_RAW_URL}}` | v2rayN、v2rayNG、Shadowrocket |
| Mihomo 订阅 | `{{MEU_MIHOMO_URL}}` | Clash Verge Rev |
| 旧版 Clash 订阅 | `{{MEU_LEGACY_URL}}` | 已安装的旧版 Clash for Windows |

### tyccc：视频优先

| 订阅类型 | 链接 | 适用软件 |
|---|---|---|
| 原始订阅 | `{{TYCCC_RAW_URL}}` | v2rayN、v2rayNG、Shadowrocket |
| Mihomo 订阅 | `{{TYCCC_MIHOMO_URL}}` | Clash Verge Rev |
| 旧版 Clash 订阅 | `{{TYCCC_LEGACY_URL}}` | 已安装的旧版 Clash for Windows |

**流量怎么分配：**MEU 的 VPS 套餐每月只有 **1000 GB**，由所有使用者共用。MEU 订阅虽然没有设置每人限额，也不代表服务器流量无限；请优先用于工作，尽量少在 MEU 上做与工作无关的大流量活动。看视频可选 tyccc，减轻 MEU 的共享流量压力。tyccc 的上述订阅目前也未设置个人限额，但 VPS 套餐可能仍有服务商的月度流量上限，不能理解成服务器绝对无限。

两台线路各有三种格式；每台设备选一条适合软件的链接即可。网页上打不开 GitHub 时，从管理员提供的离线包获取安装文件。

## 设备与软件对照

Windows 和 Mac **默认选 v2rayN**；Android 选 v2rayNG，iPhone／iPad 选 Shadowrocket。已经习惯 Clash Verge Rev 的同事可以选它。**一台设备装一款就够了。**

| 设备 | 软件 | 使用哪种订阅格式 | 离线文件 | 官方下载 |
|---|---|---|---|---|
| Windows 10/11 | **v2rayN（推荐）** | 原始订阅 | `v2rayN/Windows/v2rayN-windows-64-desktop.zip` | [7.24.9 官方文件](https://github.com/2dust/v2rayN/releases/download/7.24.9/v2rayN-windows-64-desktop.zip) |
| Windows 10/11 | Clash Verge Rev | Mihomo 订阅 | `Clash-Verge-Rev/Windows/Clash.Verge_2.5.2_x64-setup.exe` | [2.5.2 官方文件](https://github.com/clash-verge-rev/clash-verge-rev/releases/download/v2.5.2/Clash.Verge_2.5.2_x64-setup.exe) |
| Mac，Apple 芯片 | **v2rayN（推荐）** | 原始订阅 | `v2rayN/macOS/v2rayN-macos-arm64.dmg` | [7.24.9 官方文件](https://github.com/2dust/v2rayN/releases/download/7.24.9/v2rayN-macos-arm64.dmg) |
| Mac，Intel 芯片 | **v2rayN（推荐）** | 原始订阅 | `v2rayN/macOS/v2rayN-macos-64.dmg` | [7.24.9 官方文件](https://github.com/2dust/v2rayN/releases/download/7.24.9/v2rayN-macos-64.dmg) |
| Mac，Apple 芯片 | Clash Verge Rev | Mihomo 订阅 | `Clash-Verge-Rev/macOS/Clash.Verge_2.5.2_aarch64.dmg` | [2.5.2 官方文件](https://github.com/clash-verge-rev/clash-verge-rev/releases/download/v2.5.2/Clash.Verge_2.5.2_aarch64.dmg) |
| Mac，Intel 芯片 | Clash Verge Rev | Mihomo 订阅 | `Clash-Verge-Rev/macOS/Clash.Verge_2.5.2_x64.dmg` | [2.5.2 官方文件](https://github.com/clash-verge-rev/clash-verge-rev/releases/download/v2.5.2/Clash.Verge_2.5.2_x64.dmg) |
| Android | v2rayNG | 原始订阅 | `v2rayNG/Android/v2rayNG_2.2.6_arm64-v8a.apk` | [2.2.6 官方文件](https://github.com/2dust/v2rayNG/releases/download/2.2.6/v2rayNG_2.2.6_arm64-v8a.apk) |
| iPhone／iPad | Shadowrocket | 原始订阅 | App Store 安装，无 APK | [App Store 页面](https://apps.apple.com/app/shadowrocket/id932747118) |
| Linux | Clash Verge Rev | Mihomo 订阅 | 当前未存档 | [官方发布页](https://github.com/clash-verge-rev/clash-verge-rev/releases) |

普通 Windows 电脑选 `x64`。Mac 不知道芯片类型时，点屏幕左上角苹果标志 → **关于本机**：写 Apple 就选 Apple 芯片版，写 Intel 就选 Intel 版。旧版 Clash for Windows 使用“旧版 Clash 订阅”，只能显示兼容的部分节点；新电脑建议装 Clash Verge Rev。

同一软件可以分别添加 `MEU-工作` 和 `tyccc-视频` 两个订阅分组，使用时切换。**切换分组后，还需选中该分组的一条可用节点。**

## 点进对应教程，照着操作

- [Windows 安装 v2rayN](安装-v2rayN-Windows.md)
- [Mac 安装 v2rayN](安装-v2rayN-Mac.md)
- [Windows 安装 Clash Verge Rev](安装-Clash-Verge-Rev-Windows.md)
- [Mac 安装 Clash Verge Rev](安装-Clash-Verge-Rev-Mac.md)
- [Android 安装 v2rayNG](安装-v2rayNG-Android.md)
- [iPhone／iPad 安装 Shadowrocket](安装-Shadowrocket-iOS.md)
- [Linux 安装 Clash Verge Rev](安装-Clash-Verge-Rev-Linux.md)
- [已安装旧版 Clash for Windows 的导入方法](导入-旧版-Clash-for-Windows.md)

纯鸿蒙系统无法保证运行 Android APK；请向管理员确认可用客户端。遇到证书错误时，不要关闭证书校验，把错误截图发给管理员。截图前遮住订阅链接与二维码。
