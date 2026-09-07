# systemd 与日志

systemd 是 Linux 上常见的服务管理器。安装成服务的软件可以开机启动，在你退出 SSH 后继续运行。

本次服务名称是 `x-ui`。这和网页品牌名 `3x-ui` 不完全一样，命令要使用实际服务名。

```bash
systemctl is-active x-ui
systemctl status x-ui --no-pager
journalctl -u x-ui -n 50 --no-pager
```

第一条快速看是否 active；第二条看服务状态；第三条看最近 50 条日志。`--no-pager` 表示直接输出，不进入需要按 q 退出的翻页界面。

日志帮助你把现象与原因连接起来。比如“服务起不来”可能来自配置字段错误、端口占用、证书文件不存在或权限不足；只看浏览器报错常常不够。

`systemctl restart x-ui` 会重启面板及其管理的核心，可能短暂中断代理连接。修改需要重启的设置前先保存，重启后再检查运行状态。

日志可能出现客户端地址或配置细节，公开分享前同样要脱敏。

来源：[systemctl 官方手册](https://www.freedesktop.org/software/systemd/man/latest/systemctl.html)、[journalctl 官方手册](https://www.freedesktop.org/software/systemd/man/latest/journalctl.html)。
