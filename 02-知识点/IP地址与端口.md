# IP 地址与端口

IP 地址帮助网络找到一台设备；端口帮助这台设备把连接交给某个程序。可以把它们类比为一栋楼的地址和不同窗口的号码。

`203.0.113.10:443` 中，前面是地址，后面是端口。这个地址是文档示例，不能拿来连接本次服务器。

一台 VPS 可以运行多个服务：SSH 使用一个端口，管理面板使用另一个端口，代理入站还可以使用其他端口。访问面板的端口不等于客户端代理连接的端口。

端口还区分 TCP 和 UDP。TCP 443 与 UDP 443 可以由不同的监听器使用，所以 meu 的 VLESS 和 Hysteria 能同时显示 443。两个程序想同时独占同一地址上的 TCP 443，通常会发生冲突。

查看 Linux 上的监听情况：

```bash
ss -lntup
```

“监听”表示程序在等待连接；防火墙放行只表示允许连接经过。没有程序监听时，单独放行端口不会自动产生服务。

继续阅读：[[TCP与UDP]]、[[防火墙与监听地址]]。来源：[IANA 服务名和端口登记](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)、[文档示例地址 RFC 5737](https://www.rfc-editor.org/rfc/rfc5737)。
