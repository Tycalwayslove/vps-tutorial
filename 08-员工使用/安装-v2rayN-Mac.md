# Mac：安装 v2rayN 并导入 MEU 或 tyccc

返回 [软件与订阅总览](MEU-员工使用说明.md)。先选 **MEU（工作）**或 **tyccc（视频）**，再复制该线路对应格式的链接。本软件使用总览中所选线路的 **原始订阅**。

## 1. 选择正确的安装文件

点左上角苹果标志 → **关于本机**，看“芯片／处理器”：

- 显示 Apple：从离线包取 `v2rayN/macOS/v2rayN-macos-arm64.dmg`，或点[官方 Apple 芯片版](https://github.com/2dust/v2rayN/releases/download/7.24.9/v2rayN-macos-arm64.dmg)。
- 显示 Intel：取 `v2rayN/macOS/v2rayN-macos-64.dmg`，或点[官方 Intel 版](https://github.com/2dust/v2rayN/releases/download/7.24.9/v2rayN-macos-64.dmg)。

双击 `.dmg`，按照打开的窗口提示将 v2rayN 放入“应用程序”，然后从“应用程序”启动。macOS 若显示“无法打开”或“已损坏”，先确认文件来源，再联系管理员按[项目官方 macOS 说明](https://github.com/2dust/v2rayN/wiki/Release-files-introduction)处理；不要从陌生网站重新下载所谓“修复版”。

## 2. 添加订阅并连接

1. 从总览中所选线路复制 **原始订阅**。
2. 在 v2rayN 中点 **订阅分组 → 订阅分组设置 → 添加**，别名填 `MEU-工作` 或 `tyccc-视频`，在 **可选地址 (Url)** 粘贴链接并保存。
3. 点 **订阅分组 → 更新订阅**；节点出现后，在节点列表双击想用的一行，或右键该行选择“设为活动服务器”。
4. 在窗口底部的**系统代理**菜单选择“自动配置系统代理”，再用浏览器测试网页。用完后可以关闭系统代理。

![v2rayN Mac 操作顺序示意图](../Assets/员工使用/v2rayN-订阅流程.svg)

若订阅列表为空，先确认已经更新订阅。Mac 的软件界面与 Windows 版可能略有差异，找相同名称的“订阅分组”和“系统代理”即可。

来源：[v2rayN 官方发布文件说明](https://github.com/2dust/v2rayN/wiki/Release-files-introduction)、[官方订阅说明](https://github.com/2dust/v2rayN/wiki/Description-of-subscription)。图为流程示意。

## 从官方发布页选择其他版本

打开[官方 Releases 页面](https://github.com/2dust/v2rayN/releases)，选择标有 **Latest** 的正式版，展开该版本下方的 **Assets**。Apple 芯片选 `macos-arm64.dmg`；Intel 芯片选 `macos-64.dmg`。标有 **Pre-release**、`rc` 或 `AutoBuild` 的版本先不选；`.sig` 是签名文件，`Source code` 是源码归档，都不是普通用户要安装的文件。官网版本更新后，本手册已存档的离线包不会自动更新。
