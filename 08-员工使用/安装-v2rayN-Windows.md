# Windows：安装 v2rayN 并导入 MEU 或 tyccc

返回 [软件与订阅总览](MEU-员工使用说明.md)。先选 **MEU（工作）**或 **tyccc（视频）**，再复制该线路对应格式的链接。本软件使用总览中所选线路的 **原始订阅**，不用 Mihomo 链接。

## 1. 下载并打开

普通 Windows 10／11 电脑从离线包取 `v2rayN/Windows/v2rayN-windows-64-desktop.zip`，或从 [v2rayN 官方发布文件](https://github.com/2dust/v2rayN/releases/download/7.24.9/v2rayN-windows-64-desktop.zip)下载。右键压缩包选“全部解压缩”，进入解压后的文件夹，双击 `v2rayN.exe`。**不要在压缩包预览窗口里直接运行。** 若看到 Windows 安全提示，先核对文件来自上述来源，再按公司电脑的安装政策处理。

## 2. 添加订阅

1. 复制总览中所选线路的 **原始订阅**完整 HTTPS 地址。
2. 在 v2rayN 顶部点 **订阅分组 → 订阅分组设置 → 添加**。分组别名可填 `MEU-工作` 或 `tyccc-视频`，把链接贴到 **可选地址 (Url)**，保存并关闭设置窗口。
3. 再点 **订阅分组 → 更新订阅**。这是实际下载节点的一步；只保存分组，列表会保持空白。
4. 点刚添加的分组，选中一条节点并设为活动服务器，再打开底部的**系统代理**，选择“自动配置系统代理”。
5. 用浏览器打开一个平时要访问的网页确认能正常加载。用完后可关闭系统代理。

![v2rayN Windows 操作顺序示意图](../Assets/员工使用/v2rayN-订阅流程.svg)

如果没有节点，先确认执行了“更新订阅”，再检查是否误贴了 Mihomo 链接。**不要使用“从剪贴板导入分享链接”来导入整条订阅地址。**

来源：[官方发布文件说明](https://github.com/2dust/v2rayN/wiki/Release-files-introduction)、[官方订阅格式说明](https://github.com/2dust/v2rayN/wiki/Description-of-subscription)。图为本手册绘制的流程示意，不是软件截图；按钮位置以当前版本为准。
