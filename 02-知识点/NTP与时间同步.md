# NTP 与时间同步

NTP 用于让电脑时钟与时间源保持同步。服务器时间错很多时，VMess 的认证、TLS 证书有效期判断和日志分析都可能出问题。

在服务器执行 `timedatectl status`，查看 `System clock synchronized`。本次显示已同步。时区不同和时钟错误不是一回事：北京时间比 UTC 快 8 小时，两个正确时钟可以显示不同数字。

教程的实操时间按北京时间记录；证书工具常输出 UTC/GMT；服务器日志本次使用自己的时区。因此排查时必须先对齐时间，再比较客户端与服务端的错误。

不要为了让过期证书“看上去没过期”而把系统时钟往回拨。应修复续期或同步问题。

来源：[systemd timedatectl](https://www.freedesktop.org/software/systemd/man/latest/timedatectl.html)。
