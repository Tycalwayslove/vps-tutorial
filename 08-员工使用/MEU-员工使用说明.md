# MEU 软件与订阅使用说明

## 订阅链接（先选设备和软件，再复制对应类型）

**本仓库是公开的，因此下面是占位符。管理员分发的本地版会在这里显示可直接复制的 MEU 不限流量链接。** 链接先放在这里方便查找；请先看下一节选自己的设备和软件，再回到这张表复制对应类型。订阅地址是访问凭据，请勿转发到公开群聊。

| 订阅类型 | 链接 | 适用软件 |
|---|---|---|
| 原始订阅 | `{{MEU_RAW_URL}}` | v2rayN、v2rayNG、Shadowrocket |
| Mihomo 订阅 | `{{MEU_MIHOMO_URL}}` | Clash Verge Rev |
| 旧版 Clash 订阅 | `{{MEU_LEGACY_URL}}` | 已安装的旧版 Clash for Windows |

三条链接属于**同一个不限流量订阅**，只要复制适合自己软件的那一条。它们不是软件下载地址。网页上打不开 GitHub 时，直接从管理员给的 `客户端离线分发包` 获取安装文件。

## 设备与软件对照

Windows 和 Mac **默认选 v2rayN**；Android 选 v2rayNG，iPhone／iPad 选 Shadowrocket。已经习惯 Clash Verge Rev 的同事可以选它。**一台设备装一款就够了。**

| 设备 | 软件 | 使用哪条订阅 | 离线文件 | 官方下载 |
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
